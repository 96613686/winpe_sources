# GetNonSpecialPrincipalSID(ushort *,void * *)

- ea: `0x18004e8c4`
- end: `0x18004eaa5`
- name: `?GetNonSpecialPrincipalSID@@YAJPEAGPEAPEAX@Z`
- size: `481`
- prototype: `__int64 __fastcall(wchar_t *Str, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004eaa8`

## callees

- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004e8c4`
- `0x18004ef84`
- `0x1800653b4`
- `0x1800653c0`
- `0x18006541c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004e947`
- `KERNEL32!GetLastError` at `0x18004e947`
- `KERNEL32!GetComputerNameW` at `0x18004ea30`
- `KERNEL32!GetComputerNameW` at `0x18004ea30`
- `ADVAPI32!LookupAccountNameW` at `0x18004e93d`
- `ADVAPI32!LookupAccountNameW` at `0x18004e9a0`
- `ADVAPI32!LookupAccountNameW` at `0x18004e93d`
- `ADVAPI32!LookupAccountNameW` at `0x18004e9a0`

## pseudocode

```c
__int64 __fastcall GetNonSpecialPrincipalSID(wchar_t *Str, void **a2)
{
  unsigned int v4; // ebx
  void *v5; // r8
  void *v6; // rax
  WCHAR *v7; // rax
  int v8; // edx
  int v9; // ecx
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR String1[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[256]; // [rsp+250h] [rbp+150h] BYREF

  v4 = 0;
  memset_0(String1, 0, sizeof(String1));
  v5 = *a2;
  cbSid = 0;
  cchReferencedDomainName = 255;
  if ( !LookupAccountNameW(0, Str, v5, &cbSid, String1, &cchReferencedDomainName, &peUse) )
  {
    if ( GetLastError() != 122 )
      return (unsigned int)GetLastWin32Error();
    v6 = MemAlloc(cbSid);
    *a2 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
    cchReferencedDomainName = 255;
    if ( !LookupAccountNameW(0, Str, v6, &cbSid, String1, &cchReferencedDomainName, &peUse) )
      return (unsigned int)GetLastWin32Error();
  }
  if ( String1[0] )
  {
    if ( wcscmp_0(String1, L"BUILTIN") )
    {
      if ( !wcschr_0(Str, 0x5Cu) )
      {
        nSize = 0;
        if ( !(unsigned int)IsDomainController((int *)&nSize) && !nSize )
        {
          memset_0(Buffer, 0, sizeof(Buffer));
          nSize = 255;
          if ( GetComputerNameW(Buffer, &nSize) )
          {
            if ( Buffer[0] )
            {
              v7 = Buffer;
              Buffer[255] = 0;
              do
              {
                v8 = *(WCHAR *)((char *)v7 + (char *)String1 - (char *)Buffer);
                v9 = *v7 - v8;
                if ( v9 )
                  break;
                ++v7;
              }
              while ( v8 );
              if ( v9 )
              {
                MemFree(*a2);
                *a2 = 0;
                return (unsigned int)-2147022694;
              }
            }
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004e8c4  mov     [rsp-8+arg_10], rbx
0x18004e8c9  push    rbp
0x18004e8ca  push    rsi
0x18004e8cb  push    rdi
0x18004e8cc  lea     rbp, [rsp-360h]
0x18004e8d4  sub     rsp, 460h
0x18004e8db  mov     rax, cs:__security_cookie
0x18004e8e2  xor     rax, rsp
0x18004e8e5  mov     [rbp+370h+var_20], rax
0x18004e8ec  mov     rdi, rdx
0x18004e8ef  mov     rsi, rcx
0x18004e8f2  xor     edx, edx; Val
0x18004e8f4  lea     rcx, [rsp+470h+String1]; void *
0x18004e8f9  mov     r8d, 200h; Size
0x18004e8ff  xor     ebx, ebx
0x18004e901  call    memset_0
0x18004e906  mov     r8, [rdi]; Sid
0x18004e909  lea     rax, [rsp+470h+var_424]
0x18004e90e  mov     [rsp+470h+peUse], rax; peUse
0x18004e913  lea     r9, [rsp+470h+cbSid]; cbSid
0x18004e918  lea     rax, [rsp+470h+var_42C]
0x18004e91d  mov     [rsp+470h+cbSid], ebx
0x18004e921  mov     [rsp+470h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004e926  mov     rdx, rsi; lpAccountName
0x18004e929  lea     rax, [rsp+470h+String1]
0x18004e92e  mov     [rsp+470h+var_42C], 0FFh
0x18004e936  xor     ecx, ecx; lpSystemName
0x18004e938  mov     [rsp+470h+ReferencedDomainName], rax; ReferencedDomainName
0x18004e93d  call    cs:__imp_LookupAccountNameW
0x18004e943  test    eax, eax
0x18004e945  jnz     short loc_18004E9B6
0x18004e947  call    cs:__imp_GetLastError
0x18004e94d  cmp     eax, 7Ah ; 'z'
0x18004e950  jnz     short loc_18004E9AA
0x18004e952  mov     ecx, [rsp+470h+cbSid]; unsigned __int64
0x18004e956  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18004e95b  mov     [rdi], rax
0x18004e95e  test    rax, rax
0x18004e961  jnz     short loc_18004E96D
0x18004e963  mov     ebx, 8007000Eh
0x18004e968  jmp     loc_18004EA81
0x18004e96d  lea     rcx, [rsp+470h+var_424]
0x18004e972  mov     [rsp+470h+var_42C], 0FFh
0x18004e97a  mov     [rsp+470h+peUse], rcx; peUse
0x18004e97f  lea     r9, [rsp+470h+cbSid]; cbSid
0x18004e984  lea     rcx, [rsp+470h+var_42C]
0x18004e989  mov     r8, rax; Sid
0x18004e98c  mov     [rsp+470h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18004e991  mov     rdx, rsi; lpAccountName
0x18004e994  lea     rcx, [rsp+470h+String1]
0x18004e999  mov     [rsp+470h+ReferencedDomainName], rcx; ReferencedDomainName
0x18004e99e  xor     ecx, ecx; lpSystemName
0x18004e9a0  call    cs:__imp_LookupAccountNameW
0x18004e9a6  test    eax, eax
0x18004e9a8  jnz     short loc_18004E9B6
0x18004e9aa  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004e9af  mov     ebx, eax
0x18004e9b1  jmp     loc_18004EA81
0x18004e9b6  cmp     [rsp+470h+String1], bx
0x18004e9bb  jz      loc_18004EA81
0x18004e9c1  lea     rdx, aBuiltin_0; "BUILTIN"
0x18004e9c8  lea     rcx, [rsp+470h+String1]; String1
0x18004e9cd  call    wcscmp_0
0x18004e9d2  test    eax, eax
0x18004e9d4  jz      loc_18004EA81
0x18004e9da  mov     edx, 5Ch ; '\'; Ch
0x18004e9df  mov     rcx, rsi; Str
0x18004e9e2  call    wcschr_0
0x18004e9e7  test    rax, rax
0x18004e9ea  jnz     loc_18004EA81
0x18004e9f0  lea     rcx, [rsp+470h+nSize]; int *
0x18004e9f5  mov     [rsp+470h+nSize], ebx
0x18004e9f9  call    ?IsDomainController@@YAJPEAH@Z; IsDomainController(int *)
0x18004e9fe  test    eax, eax
0x18004ea00  jnz     short loc_18004EA81
0x18004ea02  cmp     [rsp+470h+nSize], ebx
0x18004ea06  jnz     short loc_18004EA81
0x18004ea08  xor     edx, edx; Val
0x18004ea0a  lea     rcx, [rbp+370h+Buffer]; void *
0x18004ea11  mov     r8d, 200h; Size
0x18004ea17  call    memset_0
0x18004ea1c  lea     rdx, [rsp+470h+nSize]; nSize
0x18004ea21  mov     [rsp+470h+nSize], 0FFh
0x18004ea29  lea     rcx, [rbp+370h+Buffer]; lpBuffer
0x18004ea30  call    cs:__imp_GetComputerNameW
0x18004ea36  test    eax, eax
0x18004ea38  jz      short loc_18004EA81
0x18004ea3a  cmp     [rbp+370h+Buffer], bx
0x18004ea41  jz      short loc_18004EA81
0x18004ea43  lea     rax, [rbp+370h+Buffer]
0x18004ea4a  mov     [rbp+370h+var_22], bx
0x18004ea51  lea     r8, [rsp+470h+String1]
0x18004ea56  sub     r8, rax
0x18004ea59  movzx   ecx, word ptr [rax]
0x18004ea5c  movzx   edx, word ptr [rax+r8]
0x18004ea61  sub     ecx, edx
0x18004ea63  jnz     short loc_18004EA6D
0x18004ea65  add     rax, 2
0x18004ea69  test    edx, edx
0x18004ea6b  jnz     short loc_18004EA59
0x18004ea6d  test    ecx, ecx
0x18004ea6f  jz      short loc_18004EA81
0x18004ea71  mov     rcx, [rdi]; lpMem
0x18004ea74  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004ea79  mov     [rdi], rbx
0x18004ea7c  mov     ebx, 8007089Ah
0x18004ea81  mov     eax, ebx
0x18004ea83  mov     rcx, [rbp+370h+var_20]
0x18004ea8a  xor     rcx, rsp; StackCookie
0x18004ea8d  call    __security_check_cookie
0x18004ea92  mov     rbx, [rsp+470h+arg_10]
0x18004ea9a  add     rsp, 460h
0x18004eaa1  pop     rdi
0x18004eaa2  pop     rsi
0x18004eaa3  pop     rbp
0x18004eaa4  retn
```
