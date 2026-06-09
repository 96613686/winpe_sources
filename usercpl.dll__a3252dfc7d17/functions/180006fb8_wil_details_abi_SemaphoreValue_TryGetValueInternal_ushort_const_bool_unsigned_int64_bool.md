# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006fb8`
- end: `0x180007250`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000504c`
- `0x18001392c`

## callees

- `0x180006074`
- `0x180006a54`
- `0x180006a74`
- `0x180006df4`
- `0x180006fb8`
- `0x180007458`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000704f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070d1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000704f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000709c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007125`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000713d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000718f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000709c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007125`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000713d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000718f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x180006fb8  push    rbp
0x180006fba  push    rbx
0x180006fbb  push    rsi
0x180006fbc  push    rdi
0x180006fbd  push    r14
0x180006fbf  push    r15
0x180006fc1  lea     rbp, [rsp-158h]
0x180006fc9  sub     rsp, 258h
0x180006fd0  mov     rax, cs:__security_cookie
0x180006fd7  xor     rax, rsp
0x180006fda  mov     [rbp+180h+var_40], rax
0x180006fe1  xor     r15d, r15d
0x180006fe4  lea     rax, [rsp+280h+Name]
0x180006fe9  mov     esi, 104h
0x180006fee  mov     [r8], r15
0x180006ff1  mov     edx, esi
0x180006ff3  mov     r14, r8
0x180006ff6  mov     r9d, 7FFFFFFEh
0x180006ffc  test    r9, r9
0x180006fff  jz      short loc_180007020
0x180007001  movzx   r8d, word ptr [rcx]
0x180007005  test    r8w, r8w
0x180007009  jz      short loc_180007020
0x18000700b  mov     [rax], r8w
0x18000700f  add     rcx, 2
0x180007013  add     rax, 2
0x180007017  dec     r9
0x18000701a  sub     rdx, 1
0x18000701e  jnz     short loc_180006FFC
0x180007020  test    rdx, rdx
0x180007023  lea     rcx, [rax-2]
0x180007027  lea     r8, aP0; "_p0"
0x18000702e  mov     rdx, rsi; unsigned __int64
0x180007031  cmovnz  rcx, rax
0x180007035  mov     [rcx], r15w
0x180007039  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000703e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007043  lea     r8, [rsp+280h+Name]; lpName
0x180007048  xor     edx, edx; bInheritHandle
0x18000704a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000704f  call    cs:__imp_OpenSemaphoreW
0x180007055  mov     rbx, rax
0x180007058  test    rax, rax
0x18000705b  jz      loc_18000719E
0x180007061  lea     rdx, [rsp+280h+var_25C]; int *
0x180007066  mov     [rsp+280h+var_25C], r15d
0x18000706b  mov     rcx, rax; hHandle
0x18000706e  mov     [rsp+280h+var_260], r15d; int
0x180007073  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007078  mov     edi, eax
0x18000707a  test    eax, eax
0x18000707c  jns     short loc_1800070B1
0x18000707e  mov     rcx, [rbp+188h]; this
0x180007085  lea     r8, aWil; "wil"
0x18000708c  mov     r9d, eax; char *
0x18000708f  mov     edx, 0D6h; void *
0x180007094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007099  mov     rcx, rbx; hObject
0x18000709c  call    cs:__imp_CloseHandle
0x1800070a2  test    eax, eax
0x1800070a4  jz      loc_18000721A
0x1800070aa  mov     eax, edi
0x1800070ac  jmp     loc_1800071C5
0x1800070b1  lea     r8, asc_180083ED8; "h"
0x1800070b8  mov     rdx, rsi; unsigned __int64
0x1800070bb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800070c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070c5  lea     r8, [rsp+280h+Name]; lpName
0x1800070ca  xor     edx, edx; bInheritHandle
0x1800070cc  mov     ecx, 1F0003h; dwDesiredAccess
0x1800070d1  call    cs:__imp_OpenSemaphoreW
0x1800070d7  mov     rdi, rax
0x1800070da  test    rax, rax
0x1800070dd  jz      loc_180007172
0x1800070e3  lea     rdx, [rsp+280h+var_260]; int *
0x1800070e8  mov     rcx, rax; hHandle
0x1800070eb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800070f0  mov     esi, eax
0x1800070f2  test    eax, eax
0x1800070f4  jns     short loc_18000713A
0x1800070f6  mov     rcx, [rbp+188h]; this
0x1800070fd  lea     r8, aWil; "wil"
0x180007104  mov     r9d, eax; char *
0x180007107  mov     edx, 0DEh; void *
0x18000710c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007111  mov     rcx, rdi; hObject
0x180007114  call    cs:__imp_CloseHandle
0x18000711a  test    eax, eax
0x18000711c  jz      loc_18000722C
0x180007122  mov     rcx, rbx; hObject
0x180007125  call    cs:__imp_CloseHandle
0x18000712b  test    eax, eax
0x18000712d  jz      loc_18000723E
0x180007133  mov     eax, esi
0x180007135  jmp     loc_1800071C5
0x18000713a  mov     rcx, rdi; hObject
0x18000713d  call    cs:__imp_CloseHandle
0x180007143  test    eax, eax
0x180007145  jz      loc_1800071E4
0x18000714b  movsxd  rax, [rsp+280h+var_25C]
0x180007150  movsxd  rcx, [rsp+280h+var_260]
0x180007155  shl     rcx, 1Fh
0x180007159  or      rcx, rax
0x18000715c  mov     [r14], rcx
0x18000715f  mov     rcx, rbx; hObject
0x180007162  call    cs:__imp_CloseHandle
0x180007168  test    eax, eax
0x18000716a  jz      loc_1800071F6
0x180007170  jmp     short loc_1800071A9
0x180007172  mov     rcx, [rbp+188h]; this
0x180007179  lea     r8, aWil; "wil"
0x180007180  mov     edx, 0DCh; void *
0x180007185  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000718a  mov     rcx, rbx; hObject
0x18000718d  mov     edi, eax
0x18000718f  call    cs:__imp_CloseHandle
0x180007195  test    eax, eax
0x180007197  jz      short loc_180007208
0x180007199  jmp     loc_1800070AA
0x18000719e  call    cs:__imp_GetLastError
0x1800071a4  cmp     eax, 2
0x1800071a7  jnz     short loc_1800071AD
0x1800071a9  xor     eax, eax
0x1800071ab  jmp     short loc_1800071C5
0x1800071ad  mov     rcx, [rbp+188h]; this
0x1800071b4  lea     r8, aWil; "wil"
0x1800071bb  mov     edx, 0D0h; void *
0x1800071c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800071c5  mov     rcx, [rbp+180h+var_40]
0x1800071cc  xor     rcx, rsp; StackCookie
0x1800071cf  call    __security_check_cookie
0x1800071d4  add     rsp, 258h
0x1800071db  pop     r15
0x1800071dd  pop     r14
0x1800071df  pop     rdi
0x1800071e0  pop     rsi
0x1800071e1  pop     rbx
0x1800071e2  pop     rbp
0x1800071e3  retn
0x1800071e4  mov     rcx, [rbp+188h]; this
0x1800071eb  mov     edx, 0A0Bh; void *
0x1800071f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071f6  mov     rcx, [rbp+188h]; this
0x1800071fd  mov     edx, 0A0Bh; void *
0x180007202  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007208  mov     rcx, [rbp+188h]; this
0x18000720f  mov     edx, 0A0Bh; void *
0x180007214  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000721a  mov     rcx, [rbp+188h]; this
0x180007221  mov     edx, 0A0Bh; void *
0x180007226  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000722c  mov     rcx, [rbp+188h]; this
0x180007233  mov     edx, 0A0Bh; void *
0x180007238  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000723e  mov     rcx, [rbp+188h]; this
0x180007245  mov     edx, 0A0Bh; void *
0x18000724a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
