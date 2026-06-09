# _lambda_dcb7487bfc76c7debce626e676faeaa0_::operator()

- ea: `0x180077698`
- end: `0x180077766`
- name: `_lambda_dcb7487bfc76c7debce626e676faeaa0_::operator()`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800804a0`

## callees

- `0x1800088e8`
- `0x180077698`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18007773b`
- `msvcrt!_wcsicmp` at `0x18007773b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007771f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007772f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007771f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007772f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800776c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800776c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077750`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180077710`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180077710`

## string_xrefs

- `0x1800776f2`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_dcb7487bfc76c7debce626e676faeaa0_::operator()(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v11; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v13; // rax
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v17; // [rsp+4Ch] [rbp+14h]
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  v17 = HIDWORD(a2);
  string = 0;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(a3, &string);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v11 = *(_DWORD *)(a1 + 8);
    if ( v17 == v11 || v11 == (unsigned int)RtlGetCurrentServiceSessionId(v9) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
      v13 = WindowsGetStringRawBuffer(string, 0);
      if ( !_wcsicmp(v13, StringRawBuffer) )
        *a4 = 1;
    }
    v10 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x739,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
      (const char *)(unsigned int)v8,
      v15);
  }
  WindowsDeleteString(string);
  return v10;
}

```

## disassembly

```asm
0x180077698  mov     [rsp+arg_0], rbx
0x18007769d  mov     [rsp+arg_8], rdx
0x1800776a2  push    rsi
0x1800776a3  push    rdi
0x1800776a4  push    r14; int
0x1800776a6  sub     rsp, 20h
0x1800776aa  mov     r14, r9
0x1800776ad  mov     rdi, r8
0x1800776b0  mov     rsi, rcx
0x1800776b3  mov     [rsp+38h+string], 0
0x1800776bc  mov     rax, [r8]
0x1800776bf  mov     rbx, [rax+30h]
0x1800776c3  xor     ecx, ecx; string
0x1800776c5  call    cs:__imp_WindowsDeleteString
0x1800776cb  mov     [rsp+38h+string], 0
0x1800776d4  lea     rdx, [rsp+38h+string]
0x1800776d9  mov     rcx, rdi
0x1800776dc  mov     rax, rbx
0x1800776df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776e4  mov     ebx, eax
0x1800776e6  test    eax, eax
0x1800776e8  jns     short loc_180077705
0x1800776ea  mov     rcx, [rsp+38h]; this
0x1800776ef  mov     r9d, eax; char *
0x1800776f2  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x1800776f9  mov     edx, 739h; void *
0x1800776fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077703  jmp     short loc_18007774B
0x180077705  mov     eax, [rsi+8]
0x180077708  cmp     dword ptr [rsp+38h+arg_8+4], eax
0x18007770c  jz      short loc_18007771A
0x18007770e  mov     ebx, eax
0x180077710  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180077716  cmp     ebx, eax
0x180077718  jnz     short loc_180077749
0x18007771a  xor     edx, edx; length
0x18007771c  mov     rcx, [rsi]; string
0x18007771f  call    cs:__imp_WindowsGetStringRawBuffer
0x180077725  mov     rbx, rax
0x180077728  xor     edx, edx; length
0x18007772a  mov     rcx, [rsp+38h+string]; string
0x18007772f  call    cs:__imp_WindowsGetStringRawBuffer
0x180077735  mov     rdx, rbx; String2
0x180077738  mov     rcx, rax; String1
0x18007773b  call    cs:__imp__wcsicmp
0x180077741  test    eax, eax
0x180077743  jnz     short loc_180077749
0x180077745  mov     byte ptr [r14], 1
0x180077749  xor     ebx, ebx
0x18007774b  mov     rcx, [rsp+38h+string]; string
0x180077750  call    cs:__imp_WindowsDeleteString
0x180077756  mov     eax, ebx
0x180077758  mov     rbx, [rsp+38h+arg_0]
0x18007775d  add     rsp, 20h
0x180077761  pop     r14
0x180077763  pop     rdi
0x180077764  pop     rsi
0x180077765  retn
```
