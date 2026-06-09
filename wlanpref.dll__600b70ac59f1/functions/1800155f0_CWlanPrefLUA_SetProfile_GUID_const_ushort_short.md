# CWlanPrefLUA::SetProfile(_GUID const *,ushort *,short)

- ea: `0x1800155f0`
- end: `0x1800156b8`
- name: `?SetProfile@CWlanPrefLUA@@UEAAJPEBU_GUID@@PEAGF@Z`
- size: `200`
- prototype: `__int64 __fastcall(CWlanPrefLUA *this, const struct _GUID *, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800155f0`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18001568f`
- `wlanapi!WlanCloseHandle` at `0x18001568f`
- `wlanapi!WlanSetProfile` at `0x18001567b`
- `wlanapi!WlanSetProfile` at `0x18001567b`
- `wlanapi!WlanOpenHandle` at `0x18001563d`
- `wlanapi!WlanOpenHandle` at `0x18001563d`

## pseudocode

```c
__int64 __fastcall CWlanPrefLUA::SetProfile(
        CWlanPrefLUA *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        __int16 a4)
{
  DWORD v6; // edi
  signed int v7; // ebx
  HANDLE hClientHandle; // [rsp+40h] [rbp-28h] BYREF
  DWORD pdwReasonCode; // [rsp+78h] [rbp+10h] BYREF
  DWORD v11; // [rsp+88h] [rbp+20h] BYREF

  hClientHandle = 0;
  pdwReasonCode = 0;
  v6 = a4 == 0 ? 2 : 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v11 = 0;
  v7 = WlanOpenHandle(2u, 0, &v11, &hClientHandle);
  if ( !v7 )
    v7 = WlanSetProfile(hClientHandle, a2, v6, a3, 0, 1, 0, &pdwReasonCode);
  if ( hClientHandle )
    WlanCloseHandle(hClientHandle, 0);
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800155f0  mov     rax, rsp
0x1800155f3  mov     [rax+8], rbx
0x1800155f7  push    rbp
0x1800155f8  push    rsi
0x1800155f9  push    rdi
0x1800155fa  sub     rsp, 50h
0x1800155fe  neg     r9w
0x180015602  mov     qword ptr [rax-28h], 0
0x18001560a  mov     ecx, 2; dwClientVersion
0x18001560f  mov     dword ptr [rax+10h], 0
0x180015616  sbb     edi, edi
0x180015618  mov     rsi, r8
0x18001561b  not     edi
0x18001561d  mov     rbp, rdx
0x180015620  and     edi, ecx
0x180015622  test    rdx, rdx
0x180015625  jz      short loc_1800156A6
0x180015627  test    r8, r8
0x18001562a  jz      short loc_1800156A6
0x18001562c  lea     r9, [rax-28h]; phClientHandle
0x180015630  mov     dword ptr [rax+20h], 0
0x180015637  lea     r8, [rax+20h]; pdwNegotiatedVersion
0x18001563b  xor     edx, edx; pReserved
0x18001563d  call    cs:__imp_WlanOpenHandle
0x180015643  mov     ebx, eax
0x180015645  test    eax, eax
0x180015647  jnz     short loc_180015683
0x180015649  mov     rcx, [rsp+68h+hClientHandle]; hClientHandle
0x18001564e  lea     rax, [rsp+68h+arg_8]
0x180015653  mov     [rsp+68h+pdwReasonCode], rax; pdwReasonCode
0x180015658  mov     r9, rsi; strProfileXml
0x18001565b  mov     [rsp+68h+pReserved], 0; pReserved
0x180015664  mov     r8d, edi; dwFlags
0x180015667  mov     [rsp+68h+bOverwrite], 1; bOverwrite
0x18001566f  mov     rdx, rbp; pInterfaceGuid
0x180015672  mov     [rsp+68h+strAllUserProfileSecurity], 0; strAllUserProfileSecurity
0x18001567b  call    cs:__imp_WlanSetProfile
0x180015681  mov     ebx, eax
0x180015683  mov     rcx, [rsp+68h+hClientHandle]; hClientHandle
0x180015688  test    rcx, rcx
0x18001568b  jz      short loc_180015695
0x18001568d  xor     edx, edx; pReserved
0x18001568f  call    cs:__imp_WlanCloseHandle
0x180015695  test    ebx, ebx
0x180015697  jle     short loc_1800156A2
0x180015699  movzx   ebx, bx
0x18001569c  or      ebx, 80070000h
0x1800156a2  mov     eax, ebx
0x1800156a4  jmp     short loc_1800156AB
0x1800156a6  mov     eax, 80070057h
0x1800156ab  mov     rbx, [rsp+68h+arg_0]
0x1800156b0  add     rsp, 50h
0x1800156b4  pop     rdi
0x1800156b5  pop     rsi
0x1800156b6  pop     rbp
0x1800156b7  retn
```
