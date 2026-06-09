# ProfileExists(_GUID &,ushort const *,bool &,bool &)

- ea: `0x180021f40`
- end: `0x180022033`
- name: `?ProfileExists@@YAJAEAU_GUID@@PEBGAEA_N2@Z`
- size: `243`
- prototype: `__int64 __fastcall(GUID *pInterfaceGuid, LPCWSTR strProfileName, bool *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002203c`

## callees

- `0x180021f40`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x180022011`
- `wlanapi!WlanCloseHandle` at `0x180022011`
- `wlanapi!WlanFreeMemory` at `0x180022000`
- `wlanapi!WlanFreeMemory` at `0x180022000`
- `wlanapi!WlanOpenHandle` at `0x180021f9e`
- `wlanapi!WlanOpenHandle` at `0x180021f9e`
- `wlanapi!WlanGetProfile` at `0x180021fd2`
- `wlanapi!WlanGetProfile` at `0x180021fd2`

## pseudocode

```c
__int64 __fastcall ProfileExists(GUID *pInterfaceGuid, LPCWSTR strProfileName, bool *a3, bool *a4)
{
  signed int Profile; // ebx
  bool v10; // zf
  DWORD pdwNegotiatedVersion; // [rsp+40h] [rbp-28h] BYREF
  void *phClientHandle; // [rsp+48h] [rbp-20h] BYREF
  LPWSTR pstrProfileXml; // [rsp+50h] [rbp-18h] BYREF
  DWORD pdwFlags; // [rsp+A8h] [rbp+40h] BYREF

  pdwNegotiatedVersion = 0;
  phClientHandle = 0;
  pstrProfileXml = 0;
  pdwFlags = 0;
  if ( !strProfileName )
    return 2147942487LL;
  *a3 = 0;
  *a4 = 0;
  Profile = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( !Profile )
  {
    Profile = WlanGetProfile(phClientHandle, pInterfaceGuid, strProfileName, 0, &pstrProfileXml, &pdwFlags, 0);
    if ( Profile )
    {
      if ( Profile == 1168 )
        Profile = 0;
    }
    else
    {
      v10 = (pdwFlags & 1) == 0;
      *a3 = 1;
      if ( !v10 )
        *a4 = 1;
    }
  }
  if ( pstrProfileXml )
    WlanFreeMemory(pstrProfileXml);
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  if ( Profile > 0 )
    return (unsigned __int16)Profile | 0x80070000;
  return (unsigned int)Profile;
}

```

## disassembly

```asm
0x180021f40  push    rbp
0x180021f42  push    rbx
0x180021f43  push    rsi
0x180021f44  push    rdi
0x180021f45  push    r14
0x180021f47  push    r15
0x180021f49  mov     rbp, rsp
0x180021f4c  sub     rsp, 68h
0x180021f50  mov     [rbp+pdwNegotiatedVersion], 0
0x180021f57  mov     rdi, r9
0x180021f5a  mov     [rbp+phClientHandle], 0
0x180021f62  mov     rsi, r8
0x180021f65  mov     [rbp+var_18], 0
0x180021f6d  mov     r14, rdx
0x180021f70  mov     [rbp+arg_8], 0
0x180021f77  mov     r15, rcx
0x180021f7a  test    rdx, rdx
0x180021f7d  jnz     short loc_180021F89
0x180021f7f  mov     eax, 80070057h
0x180021f84  jmp     loc_180022026
0x180021f89  mov     byte ptr [r8], 0
0x180021f8d  xor     edx, edx; pReserved
0x180021f8f  mov     byte ptr [r9], 0
0x180021f93  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180021f97  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180021f9b  lea     ecx, [rdx+2]; dwClientVersion
0x180021f9e  call    cs:__imp_WlanOpenHandle
0x180021fa4  mov     ebx, eax
0x180021fa6  test    eax, eax
0x180021fa8  jnz     short loc_180021FF7
0x180021faa  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021fae  lea     rax, [rbp+arg_8]
0x180021fb2  mov     [rsp+68h+pdwGrantedAccess], 0; pdwGrantedAccess
0x180021fbb  xor     r9d, r9d; pReserved
0x180021fbe  mov     [rsp+68h+pdwFlags], rax; pdwFlags
0x180021fc3  mov     r8, r14; strProfileName
0x180021fc6  lea     rax, [rbp+var_18]
0x180021fca  mov     rdx, r15; pInterfaceGuid
0x180021fcd  mov     [rsp+68h+pstrProfileXml], rax; pstrProfileXml
0x180021fd2  call    cs:__imp_WlanGetProfile
0x180021fd8  mov     ebx, eax
0x180021fda  test    eax, eax
0x180021fdc  jnz     short loc_180021FEC
0x180021fde  test    byte ptr [rbp+arg_8], 1
0x180021fe2  mov     byte ptr [rsi], 1
0x180021fe5  jz      short loc_180021FF7
0x180021fe7  mov     byte ptr [rdi], 1
0x180021fea  jmp     short loc_180021FF7
0x180021fec  xor     eax, eax
0x180021fee  cmp     ebx, 490h
0x180021ff4  cmovz   ebx, eax
0x180021ff7  mov     rcx, [rbp+var_18]; pMemory
0x180021ffb  test    rcx, rcx
0x180021ffe  jz      short loc_180022006
0x180022000  call    cs:__imp_WlanFreeMemory
0x180022006  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18002200a  test    rcx, rcx
0x18002200d  jz      short loc_180022017
0x18002200f  xor     edx, edx; pReserved
0x180022011  call    cs:__imp_WlanCloseHandle
0x180022017  test    ebx, ebx
0x180022019  jle     short loc_180022024
0x18002201b  movzx   ebx, bx
0x18002201e  or      ebx, 80070000h
0x180022024  mov     eax, ebx
0x180022026  add     rsp, 68h
0x18002202a  pop     r15
0x18002202c  pop     r14
0x18002202e  pop     rdi
0x18002202f  pop     rsi
0x180022030  pop     rbx
0x180022031  pop     rbp
0x180022032  retn
```
