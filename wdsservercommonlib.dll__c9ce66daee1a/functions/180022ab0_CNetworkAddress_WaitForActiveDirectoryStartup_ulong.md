# CNetworkAddress::WaitForActiveDirectoryStartup(ulong)

- ea: `0x180022ab0`
- end: `0x180022b94`
- name: `?WaitForActiveDirectoryStartup@CNetworkAddress@@SAKK@Z`
- size: `228`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022ab0`
- `0x180023850`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022b6b`
- `KERNEL32!GetLastError` at `0x180022b6b`
- `KERNEL32!WaitForSingleObject` at `0x180022b5b`
- `KERNEL32!WaitForSingleObject` at `0x180022b5b`
- `KERNEL32!CloseHandle` at `0x180022b86`
- `KERNEL32!CloseHandle` at `0x180022b86`
- `KERNEL32!Sleep` at `0x180022b16`
- `KERNEL32!Sleep` at `0x180022b16`
- `KERNEL32!OpenEventW` at `0x180022aff`
- `KERNEL32!OpenEventW` at `0x180022aff`
- `ntdll!RtlGetNtProductType` at `0x180022ace`
- `ntdll!RtlGetNtProductType` at `0x180022ace`

## string_xrefs

- `0x180022af1`: `NTDSInitialSyncsCompleted`

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
0x180022ab0  mov     rax, rsp
0x180022ab3  mov     [rax+8], rbx
0x180022ab7  mov     [rax+18h], rbp
0x180022abb  push    rsi
0x180022abc  push    rdi
0x180022abd  push    r14
0x180022abf  sub     rsp, 20h
0x180022ac3  mov     ebp, ecx
0x180022ac5  xor     ebx, ebx
0x180022ac7  lea     rcx, [rax+10h]; ProductType
0x180022acb  mov     [rax+10h], ebx
0x180022ace  call    cs:__imp_RtlGetNtProductType
0x180022ad5  nop     dword ptr [rax+rax+00h]
0x180022ada  test    al, al
0x180022adc  jz      short loc_180022B36
0x180022ade  cmp     [rsp+38h+arg_8], 2
0x180022ae3  jnz     short loc_180022B36
0x180022ae5  xor     ecx, ecx; struct _FILETIME *
0x180022ae7  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180022aec  mov     rdi, rax
0x180022aef  jmp     short loc_180022B22
0x180022af1  lea     r8, aNtdsinitialsyn; "NTDSInitialSyncsCompleted"
0x180022af8  xor     edx, edx; bInheritHandle
0x180022afa  mov     ecx, 100000h; dwDesiredAccess
0x180022aff  call    cs:__imp_OpenEventW
0x180022b06  nop     dword ptr [rax+rax+00h]
0x180022b0b  mov     rsi, rax
0x180022b0e  test    rax, rax
0x180022b11  jnz     short loc_180022B4C
0x180022b13  lea     ecx, [rax+64h]; dwMilliseconds
0x180022b16  call    cs:__imp_Sleep
0x180022b1d  nop     dword ptr [rax+rax+00h]
0x180022b22  xor     ecx, ecx; struct _FILETIME *
0x180022b24  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180022b29  sub     rax, rdi
0x180022b2c  cmp     rax, rbp
0x180022b2f  jb      short loc_180022AF1
0x180022b31  mov     ebx, 5B4h
0x180022b36  mov     rbp, [rsp+38h+arg_10]
0x180022b3b  mov     eax, ebx
0x180022b3d  mov     rbx, [rsp+38h+arg_0]
0x180022b42  add     rsp, 20h
0x180022b46  pop     r14
0x180022b48  pop     rdi
0x180022b49  pop     rsi
0x180022b4a  retn
0x180022b4c  xor     ecx, ecx; struct _FILETIME *
0x180022b4e  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180022b53  sub     edi, eax
0x180022b55  mov     rcx, rsi; hHandle
0x180022b58  lea     edx, [rdi+rbp]; dwMilliseconds
0x180022b5b  call    cs:__imp_WaitForSingleObject
0x180022b62  nop     dword ptr [rax+rax+00h]
0x180022b67  test    eax, eax
0x180022b69  jz      short loc_180022B83
0x180022b6b  call    cs:__imp_GetLastError
0x180022b72  nop     dword ptr [rax+rax+00h]
0x180022b77  test    eax, eax
0x180022b79  mov     ecx, 5B4h
0x180022b7e  cmovz   eax, ecx
0x180022b81  mov     ebx, eax
0x180022b83  mov     rcx, rsi; hObject
0x180022b86  call    cs:__imp_CloseHandle
0x180022b8d  nop     dword ptr [rax+rax+00h]
0x180022b92  jmp     short loc_180022B36
```
