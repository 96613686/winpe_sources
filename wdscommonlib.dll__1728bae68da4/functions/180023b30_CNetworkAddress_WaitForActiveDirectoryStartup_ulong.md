# CNetworkAddress::WaitForActiveDirectoryStartup(ulong)

- ea: `0x180023b30`
- end: `0x180023c14`
- name: `?WaitForActiveDirectoryStartup@CNetworkAddress@@SAKK@Z`
- size: `228`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180023b30`
- `0x180024920`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x180023b7f`
- `KERNEL32!OpenEventW` at `0x180023b7f`
- `KERNEL32!GetLastError` at `0x180023beb`
- `KERNEL32!GetLastError` at `0x180023beb`
- `KERNEL32!WaitForSingleObject` at `0x180023bdb`
- `KERNEL32!WaitForSingleObject` at `0x180023bdb`
- `KERNEL32!CloseHandle` at `0x180023c06`
- `KERNEL32!CloseHandle` at `0x180023c06`
- `KERNEL32!Sleep` at `0x180023b96`
- `KERNEL32!Sleep` at `0x180023b96`
- `ntdll!RtlGetNtProductType` at `0x180023b4e`
- `ntdll!RtlGetNtProductType` at `0x180023b4e`

## string_xrefs

- `0x180023b71`: `NTDSInitialSyncsCompleted`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::WaitForActiveDirectoryStartup(unsigned int a1)
{
  unsigned __int64 v1; // rbp
  DWORD v2; // ebx
  unsigned __int64 v3; // rdi
  HANDLE v4; // rsi
  int v6; // eax
  DWORD LastError; // eax
  int v8; // [rsp+48h] [rbp+10h] BYREF

  v1 = a1;
  v2 = 0;
  v8 = 0;
  if ( RtlGetNtProductType((PNT_PRODUCT_TYPE)&v8) && v8 == 2 )
  {
    v3 = CDate::FileTimeToMSec(0);
    while ( 1 )
    {
      if ( CDate::FileTimeToMSec(0) - v3 >= v1 )
        return 1460;
      v4 = OpenEventW(0x100000u, 0, L"NTDSInitialSyncsCompleted");
      if ( v4 )
        break;
      Sleep(0x64u);
    }
    v6 = CDate::FileTimeToMSec(0);
    if ( WaitForSingleObject(v4, v3 - v6 + v1) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1460;
      v2 = LastError;
    }
    CloseHandle(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180023b30  mov     rax, rsp
0x180023b33  mov     [rax+8], rbx
0x180023b37  mov     [rax+18h], rbp
0x180023b3b  push    rsi
0x180023b3c  push    rdi
0x180023b3d  push    r14
0x180023b3f  sub     rsp, 20h
0x180023b43  mov     ebp, ecx
0x180023b45  xor     ebx, ebx
0x180023b47  lea     rcx, [rax+10h]; ProductType
0x180023b4b  mov     [rax+10h], ebx
0x180023b4e  call    cs:__imp_RtlGetNtProductType
0x180023b55  nop     dword ptr [rax+rax+00h]
0x180023b5a  test    al, al
0x180023b5c  jz      short loc_180023BB6
0x180023b5e  cmp     [rsp+38h+arg_8], 2
0x180023b63  jnz     short loc_180023BB6
0x180023b65  xor     ecx, ecx; struct _FILETIME *
0x180023b67  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180023b6c  mov     rdi, rax
0x180023b6f  jmp     short loc_180023BA2
0x180023b71  lea     r8, aNtdsinitialsyn; "NTDSInitialSyncsCompleted"
0x180023b78  xor     edx, edx; bInheritHandle
0x180023b7a  mov     ecx, 100000h; dwDesiredAccess
0x180023b7f  call    cs:__imp_OpenEventW
0x180023b86  nop     dword ptr [rax+rax+00h]
0x180023b8b  mov     rsi, rax
0x180023b8e  test    rax, rax
0x180023b91  jnz     short loc_180023BCC
0x180023b93  lea     ecx, [rax+64h]; dwMilliseconds
0x180023b96  call    cs:__imp_Sleep
0x180023b9d  nop     dword ptr [rax+rax+00h]
0x180023ba2  xor     ecx, ecx; struct _FILETIME *
0x180023ba4  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180023ba9  sub     rax, rdi
0x180023bac  cmp     rax, rbp
0x180023baf  jb      short loc_180023B71
0x180023bb1  mov     ebx, 5B4h
0x180023bb6  mov     rbp, [rsp+38h+arg_10]
0x180023bbb  mov     eax, ebx
0x180023bbd  mov     rbx, [rsp+38h+arg_0]
0x180023bc2  add     rsp, 20h
0x180023bc6  pop     r14
0x180023bc8  pop     rdi
0x180023bc9  pop     rsi
0x180023bca  retn
0x180023bcc  xor     ecx, ecx; struct _FILETIME *
0x180023bce  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180023bd3  sub     edi, eax
0x180023bd5  mov     rcx, rsi; hHandle
0x180023bd8  lea     edx, [rdi+rbp]; dwMilliseconds
0x180023bdb  call    cs:__imp_WaitForSingleObject
0x180023be2  nop     dword ptr [rax+rax+00h]
0x180023be7  test    eax, eax
0x180023be9  jz      short loc_180023C03
0x180023beb  call    cs:__imp_GetLastError
0x180023bf2  nop     dword ptr [rax+rax+00h]
0x180023bf7  test    eax, eax
0x180023bf9  mov     ecx, 5B4h
0x180023bfe  cmovz   eax, ecx
0x180023c01  mov     ebx, eax
0x180023c03  mov     rcx, rsi; hObject
0x180023c06  call    cs:__imp_CloseHandle
0x180023c0d  nop     dword ptr [rax+rax+00h]
0x180023c12  jmp     short loc_180023BB6
```
