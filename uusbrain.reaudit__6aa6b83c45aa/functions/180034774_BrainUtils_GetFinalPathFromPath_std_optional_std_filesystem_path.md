# BrainUtils::GetFinalPathFromPath(std::optional<std::filesystem::path>)

- ea: `0x180034774`
- end: `0x18003490d`
- name: `?GetFinalPathFromPath@BrainUtils@@SA?AV?$optional@Vpath@filesystem@std@@@std@@V23@@Z`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x18003a00c`

## callees

- `0x180028728`
- `0x180029644`
- `0x18003460c`
- `0x180034774`
- `0x18003dda4`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034822`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034822`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BrainUtils::GetFinalPathFromPath(__int64 a1, __int64 a2)
{
  _BYTE *v4; // r14
  const WCHAR *v5; // rcx
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE FileW; // r15
  _OWORD *v10; // rax
  LPCWSTR lpFileName[4]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v13[40]; // [rsp+80h] [rbp-78h] BYREF
  _OWORD v14[2]; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v15 = a2;
  v4 = (_BYTE *)(a2 + 32);
  if ( !*(_BYTE *)(a2 + 32) )
  {
    *(_BYTE *)(a1 + 32) = 0;
LABEL_12:
    if ( *v4 )
      std::wstring::_Tidy_deallocate(a2);
    return a1;
  }
  std::wstring::wstring(v13, a2);
  std::wstring::wstring(lpFileName, v13);
  v5 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v5 = lpFileName[0];
  FileW = CreateFileW(v5, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v6, v7, v8);
  std::wstring::_Tidy_deallocate(lpFileName);
  std::wstring::_Tidy_deallocate(v13);
  if ( FileW == (HANDLE)-1LL )
  {
    *(_BYTE *)(a1 + 32) = 0;
    goto LABEL_12;
  }
  v10 = BrainUtils::ConvertHandleToPath(v14, FileW);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *v10;
  *(_OWORD *)(a1 + 16) = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 7;
  *(_WORD *)v10 = 0;
  *(_BYTE *)(a1 + 32) = 1;
  std::wstring::_Tidy_deallocate(v14);
  if ( *v4 )
    std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x180034774  mov     r11, rsp
0x180034777  mov     [r11+18h], rbx
0x18003477b  mov     [r11+20h], rsi
0x18003477f  push    rdi
0x180034780  push    r14
0x180034782  push    r15
0x180034784  sub     rsp, 0E0h
0x18003478b  mov     rax, cs:__security_cookie
0x180034792  xor     rax, rsp
0x180034795  mov     [rsp+0F8h+var_28], rax
0x18003479d  mov     rsi, rdx
0x1800347a0  mov     rdi, rcx
0x1800347a3  mov     [rsp+0F8h+var_B0], rcx
0x1800347a8  mov     [r11-30h], rdx
0x1800347ac  xor     ebx, ebx
0x1800347ae  lea     r14, [rdx+20h]
0x1800347b2  mov     [rsp+0F8h+var_A8], r14
0x1800347b7  cmp     [r14], bl
0x1800347ba  jnz     short loc_1800347C4
0x1800347bc  mov     [rcx+20h], bl
0x1800347bf  jmp     loc_1800348D4
0x1800347c4  lea     rcx, [rsp+0F8h+var_78]
0x1800347cc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800347d1  lea     rax, [rsp+0F8h+var_78]
0x1800347d9  mov     [rsp+0F8h+var_A0], rax
0x1800347de  lea     rdx, [rsp+0F8h+var_78]
0x1800347e6  lea     rcx, [rsp+0F8h+lpFileName]
0x1800347eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800347f0  lea     rcx, [rsp+0F8h+lpFileName]
0x1800347f5  cmp     [rsp+0F8h+var_80], 7
0x1800347fb  cmova   rcx, [rsp+0F8h+lpFileName]; lpFileName
0x180034801  mov     [rsp+0F8h+hTemplateFile], rbx; hTemplateFile
0x180034806  mov     [rsp+0F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003480e  mov     [rsp+0F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180034816  xor     r9d, r9d; lpSecurityAttributes
0x180034819  mov     edx, 80000000h; dwDesiredAccess
0x18003481e  lea     r8d, [r9+7]; dwShareMode
0x180034822  call    cs:__imp_CreateFileW
0x180034828  mov     r15, rax
0x18003482b  mov     rcx, [rsp+0F8h]; this
0x180034833  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034837  jnz     short loc_18003483E
0x180034839  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003483e  lea     rcx, [rsp+0F8h+lpFileName]
0x180034843  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034848  nop
0x180034849  lea     rcx, [rsp+0F8h+var_78]
0x180034851  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034856  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18003485a  jz      short loc_1800348BB
0x18003485c  mov     rdx, r15
0x18003485f  lea     rcx, [rsp+0F8h+var_50]
0x180034867  call    ?ConvertHandleToPath@BrainUtils@@SA?AVpath@filesystem@std@@PEAX@Z; BrainUtils::ConvertHandleToPath(void *)
0x18003486c  xorps   xmm0, xmm0
0x18003486f  movups  xmmword ptr [rdi], xmm0
0x180034872  mov     [rdi+10h], rbx
0x180034876  mov     [rdi+18h], rbx
0x18003487a  movups  xmm0, xmmword ptr [rax]
0x18003487d  movups  xmmword ptr [rdi], xmm0
0x180034880  movups  xmm1, xmmword ptr [rax+10h]
0x180034884  movups  xmmword ptr [rdi+10h], xmm1
0x180034888  mov     [rax+10h], rbx
0x18003488c  mov     qword ptr [rax+18h], 7
0x180034894  mov     [rax], bx
0x180034897  mov     byte ptr [rdi+20h], 1
0x18003489b  lea     rcx, [rsp+0F8h+var_50]
0x1800348a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800348a8  nop
0x1800348a9  cmp     [r14], bl
0x1800348ac  jz      short loc_1800348B6
0x1800348ae  mov     rcx, rsi
0x1800348b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800348b6  mov     rax, rdi
0x1800348b9  jmp     short loc_1800348E4
0x1800348bb  jmp     short loc_1800348D1
0x1800348bd  xor     ebx, ebx
0x1800348bf  mov     rdi, [rsp+0F8h+var_B0]
0x1800348c4  mov     rsi, [rsp+0F8h+var_30]
0x1800348cc  mov     r14, [rsp+0F8h+var_A8]
0x1800348d1  mov     [rdi+20h], bl
0x1800348d4  cmp     [r14], bl
0x1800348d7  jz      short loc_1800348E1
0x1800348d9  mov     rcx, rsi
0x1800348dc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800348e1  mov     rax, rdi
0x1800348e4  mov     rcx, [rsp+0F8h+var_28]
0x1800348ec  xor     rcx, rsp; StackCookie
0x1800348ef  call    __security_check_cookie
0x1800348f4  lea     r11, [rsp+0F8h+var_18]
0x1800348fc  mov     rbx, [r11+30h]
0x180034900  mov     rsi, [r11+38h]
0x180034904  mov     rsp, r11
0x180034907  pop     r15
0x180034909  pop     r14
0x18003490b  pop     rdi
0x18003490c  retn
```
