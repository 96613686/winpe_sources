# sub_18001BDFC

- ea: `0x18001bdfc`
- end: `0x18001bf71`
- name: `sub_18001BDFC`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001e04c`

## callees

- `0x18001bdfc`
- `0x180038bdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001bf55`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001bf55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001be80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001be80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001be9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001beba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bed5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001be9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001beba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bed5`

## string_xrefs

- `0x18001be73`: `powrprof.dll`
- `0x18001beaf`: `PowerReadACValue`
- `0x18001beca`: `PowerReadDCValue`

## pseudocode

```c
HMODULE __fastcall sub_18001BDFC(__int64 a1)
{
  HMODULE result; // rax
  DWORD (__stdcall *PowerGetActiveScheme)(HKEY, GUID **); // rax
  HMODULE v4; // rcx
  DWORD (__stdcall *PowerReadACValue)(HKEY, const GUID *, const GUID *, const GUID *, PULONG, LPBYTE, LPDWORD); // rax
  HMODULE v6; // rcx
  int v7; // [rsp+50h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 44) = 2;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 1;
  *(_DWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 124) = xmmword_18003E1D0;
  result = (HMODULE)sub_180038BDC();
  if ( (unsigned int)dword_18004FA04 >= 2 )
  {
    result = LoadLibraryExW(L"powrprof.dll", 0, 0x800u);
    *(_QWORD *)(a1 + 80) = result;
    if ( result )
    {
      PowerGetActiveScheme = (DWORD (__stdcall *)(HKEY, GUID **))GetProcAddress(result, "PowerGetActiveScheme");
      v4 = *(HMODULE *)(a1 + 80);
      *(_QWORD *)(a1 + 88) = PowerGetActiveScheme;
      PowerReadACValue = (DWORD (__stdcall *)(HKEY, const GUID *, const GUID *, const GUID *, PULONG, LPBYTE, LPDWORD))GetProcAddress(v4, "PowerReadACValue");
      v6 = *(HMODULE *)(a1 + 80);
      *(_QWORD *)(a1 + 96) = PowerReadACValue;
      result = (HMODULE)GetProcAddress(v6, "PowerReadDCValue");
      *(_QWORD *)(a1 + 104) = result;
    }
    if ( *(_QWORD *)(a1 + 88) )
    {
      if ( *(_QWORD *)(a1 + 96) )
      {
        if ( *(_QWORD *)(a1 + 104) )
        {
          result = (HMODULE)CreateEventW(0, 0, 0, 0);
          *(_QWORD *)(a1 + 48) = result;
          if ( result )
          {
            result = (HMODULE)CreateEventW(0, 0, 0, 0);
            *(_QWORD *)(a1 + 56) = result;
            if ( result )
            {
              v7 = 0;
              result = (HMODULE)o__beginthreadex(0, 0, sub_18001CCB0, a1, 0, &v7);
              *(_QWORD *)(a1 + 64) = result;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001bdfc  mov     [rsp+arg_8], rbx
0x18001be01  push    rdi
0x18001be02  sub     rsp, 40h
0x18001be06  xor     edi, edi
0x18001be08  mov     dword ptr [rcx+2Ch], 2
0x18001be0f  xor     eax, eax
0x18001be11  mov     [rcx+30h], rdi
0x18001be15  mov     [rsp+48h+var_18+2], rax
0x18001be1a  mov     rbx, rcx
0x18001be1d  mov     [rsp+48h+var_E], ax
0x18001be22  mov     eax, [rsp+38h]
0x18001be26  mov     [rcx+38h], rdi
0x18001be2a  mov     [rcx+40h], rdi
0x18001be2e  mov     [rcx+50h], rdi
0x18001be32  mov     [rcx+58h], rdi
0x18001be36  mov     [rcx+60h], rdi
0x18001be3a  mov     [rcx+68h], rdi
0x18001be3e  mov     word ptr [rsp+48h+var_18], 1
0x18001be45  movsd   xmm0, [rsp+48h+var_18]
0x18001be4b  movsd   qword ptr [rcx+70h], xmm0
0x18001be50  mov     [rcx+78h], eax
0x18001be53  movups  xmm0, cs:xmmword_18003E1D0
0x18001be5a  movdqu  xmmword ptr [rcx+7Ch], xmm0
0x18001be5f  call    sub_180038BDC
0x18001be64  cmp     cs:dword_18004FA04, 2
0x18001be6b  jb      loc_18001BF65
0x18001be71  xor     edx, edx; hFile
0x18001be73  lea     rcx, aPowrprofDll; "powrprof.dll"
0x18001be7a  mov     r8d, 800h; dwFlags
0x18001be80  call    cs:LoadLibraryExW
0x18001be87  nop     dword ptr [rax+rax+00h]
0x18001be8c  mov     [rbx+50h], rax
0x18001be90  test    rax, rax
0x18001be93  jz      short loc_18001BEE5
0x18001be95  lea     rdx, aPowergetactive; "PowerGetActiveScheme"
0x18001be9c  mov     rcx, rax; hModule
0x18001be9f  call    cs:GetProcAddress
0x18001bea6  nop     dword ptr [rax+rax+00h]
0x18001beab  mov     rcx, [rbx+50h]; hModule
0x18001beaf  lea     rdx, aPowerreadacval; "PowerReadACValue"
0x18001beb6  mov     [rbx+58h], rax
0x18001beba  call    cs:GetProcAddress
0x18001bec1  nop     dword ptr [rax+rax+00h]
0x18001bec6  mov     rcx, [rbx+50h]; hModule
0x18001beca  lea     rdx, aPowerreaddcval; "PowerReadDCValue"
0x18001bed1  mov     [rbx+60h], rax
0x18001bed5  call    cs:GetProcAddress
0x18001bedc  nop     dword ptr [rax+rax+00h]
0x18001bee1  mov     [rbx+68h], rax
0x18001bee5  cmp     [rbx+58h], rdi
0x18001bee9  jz      short loc_18001BF65
0x18001beeb  cmp     [rbx+60h], rdi
0x18001beef  jz      short loc_18001BF65
0x18001bef1  cmp     [rbx+68h], rdi
0x18001bef5  jz      short loc_18001BF65
0x18001bef7  xor     r9d, r9d; lpName
0x18001befa  xor     r8d, r8d; bInitialState
0x18001befd  xor     edx, edx; bManualReset
0x18001beff  xor     ecx, ecx; lpEventAttributes
0x18001bf01  call    cs:CreateEventW
0x18001bf08  nop     dword ptr [rax+rax+00h]
0x18001bf0d  mov     [rbx+30h], rax
0x18001bf11  test    rax, rax
0x18001bf14  jz      short loc_18001BF65
0x18001bf16  xor     r9d, r9d; lpName
0x18001bf19  xor     r8d, r8d; bInitialState
0x18001bf1c  xor     edx, edx; bManualReset
0x18001bf1e  xor     ecx, ecx; lpEventAttributes
0x18001bf20  call    cs:CreateEventW
0x18001bf27  nop     dword ptr [rax+rax+00h]
0x18001bf2c  mov     [rbx+38h], rax
0x18001bf30  test    rax, rax
0x18001bf33  jz      short loc_18001BF65
0x18001bf35  lea     rax, [rsp+48h+arg_0]
0x18001bf3a  mov     [rsp+48h+arg_0], edi
0x18001bf3e  mov     [rsp+48h+var_20], rax
0x18001bf43  lea     r8, sub_18001CCB0
0x18001bf4a  mov     r9, rbx
0x18001bf4d  mov     [rsp+48h+var_28], edi
0x18001bf51  xor     edx, edx
0x18001bf53  xor     ecx, ecx
0x18001bf55  call    cs:_o__beginthreadex
0x18001bf5c  nop     dword ptr [rax+rax+00h]
0x18001bf61  mov     [rbx+40h], rax
0x18001bf65  mov     rbx, [rsp+48h+arg_8]
0x18001bf6a  add     rsp, 40h
0x18001bf6e  pop     rdi
0x18001bf6f  retn
```
