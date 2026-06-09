# PolicyTransforms::PersistPauseUpdatesState(wchar_t const *,PauseUpdateType,ulong,tagEnterprisePolicyValue_V1 *)

- ea: `0x1800176d4`
- end: `0x1800177fc`
- name: `?PersistPauseUpdatesState@PolicyTransforms@@SAJPEB_WW4PauseUpdateType@@KPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017900`
- `0x180017950`

## callees

- `0x1800176d4`
- `0x18001f6c8`
- `0x18001f818`
- `0x18002c898`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017769`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017779`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017769`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017779`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PolicyTransforms::PersistPauseUpdatesState(
        const wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  BOOL v6; // edi
  int v7; // eax
  __int64 v8; // rcx
  __int64 result; // rax
  LONG v10; // ebx
  LONG v11; // eax
  unsigned int v12; // edx
  FILETIME FileTime2; // [rsp+20h] [rbp-20h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-18h] BYREF
  FILETIME v15; // [rsp+30h] [rbp-10h] BYREF

  FileTime1 = 0;
  FileTime2 = 0;
  v15 = 0;
  v6 = 1;
  if ( !a1 || !a4 )
    return 2147500035LL;
  v7 = *(_DWORD *)(a4 + 4);
  if ( v7 == 1 )
  {
    v8 = *(_QWORD *)(a4 + 24);
    FileTime1 = *(FILETIME *)(a4 + 40);
    result = StringToFileTime(v8, &FileTime2, 0);
    if ( (int)result < 0 )
      return result;
    v15 = (FILETIME)(*(_QWORD *)&FileTime2 + 30240000000000LL);
    v10 = CompareFileTime(&FileTime1, &FileTime2);
    v11 = CompareFileTime(&FileTime1, &v15);
    v12 = 0;
    if ( v10 == -1 )
    {
      v6 = v11 != -1;
    }
    else
    {
      LOBYTE(v12) = v11 == -1;
      if ( v11 != -1 )
        v12 = 2;
    }
  }
  else
  {
    v12 = 0;
    if ( !v7 )
      v12 = 0;
  }
  result = PolicyHelpers::PersistPauseStatus((const wchar_t *)a2, v12);
  if ( (int)result >= 0 && (!v6 || FileTime2.dwLowDateTime || FileTime2.dwHighDateTime) )
    return PolicyHelpers::PersistPauseDate(a1, FileTime2, v6);
  return result;
}

```

## disassembly

```asm
0x1800176d4  mov     [rsp-28h+arg_8], rbx
0x1800176d9  mov     [rsp-28h+arg_10], rsi
0x1800176de  push    rbp
0x1800176df  push    rdi
0x1800176e0  push    r12
0x1800176e2  push    r14
0x1800176e4  push    r15
0x1800176e6  mov     rbp, rsp
0x1800176e9  sub     rsp, 40h
0x1800176ed  mov     rax, cs:__security_cookie
0x1800176f4  xor     rax, rsp
0x1800176f7  mov     [rbp+var_8], rax
0x1800176fb  xor     r12d, r12d
0x1800176fe  mov     r15d, edx
0x180017701  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x180017705  mov     r14, rcx
0x180017708  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x18001770c  mov     qword ptr [rbp+var_10.dwLowDateTime], r12
0x180017710  lea     edi, [r12+1]
0x180017715  test    rcx, rcx
0x180017718  jz      loc_1800177D2
0x18001771e  test    r9, r9
0x180017721  jz      loc_1800177D2
0x180017727  mov     eax, [r9+4]
0x18001772b  cmp     eax, edi
0x18001772d  jnz     short loc_18001779E
0x18001772f  mov     rax, [r9+28h]
0x180017733  lea     rdx, [rbp+FileTime2]
0x180017737  mov     rcx, [r9+18h]
0x18001773b  xor     r8d, r8d
0x18001773e  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180017742  call    StringToFileTime
0x180017747  test    eax, eax
0x180017749  js      loc_1800177D7
0x18001774f  mov     rcx, 1B80CC754000h
0x180017759  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18001775d  add     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180017761  mov     qword ptr [rbp+var_10.dwLowDateTime], rcx
0x180017765  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180017769  call    cs:__imp_CompareFileTime
0x18001776f  lea     rdx, [rbp+var_10]; lpFileTime2
0x180017773  mov     ebx, eax
0x180017775  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180017779  call    cs:__imp_CompareFileTime
0x18001777f  mov     edx, r12d
0x180017782  cmp     ebx, 0FFFFFFFFh
0x180017785  jz      short loc_180017794
0x180017787  cmp     eax, 0FFFFFFFFh
0x18001778a  setz    dl
0x18001778d  jz      short loc_1800177A7
0x18001778f  lea     edx, [rdi+1]
0x180017792  jmp     short loc_1800177A7
0x180017794  cmp     eax, 0FFFFFFFFh
0x180017797  jnz     short loc_1800177A7
0x180017799  mov     edi, r12d
0x18001779c  jmp     short loc_1800177A7
0x18001779e  test    eax, eax
0x1800177a0  mov     edx, r12d
0x1800177a3  cmovz   edx, r12d
0x1800177a7  mov     ecx, r15d
0x1800177aa  call    ?PersistPauseStatus@PolicyHelpers@@SAJW4PauseUpdateType@@K@Z; PolicyHelpers::PersistPauseStatus(PauseUpdateType,ulong)
0x1800177af  test    eax, eax
0x1800177b1  js      short loc_1800177D7
0x1800177b3  mov     rdx, qword ptr [rbp+FileTime2.dwLowDateTime]; struct _FILETIME
0x1800177b7  test    edi, edi
0x1800177b9  jz      short loc_1800177C5
0x1800177bb  test    edx, edx
0x1800177bd  jnz     short loc_1800177C5
0x1800177bf  cmp     [rbp+FileTime2.dwHighDateTime], r12d
0x1800177c3  jz      short loc_1800177D7
0x1800177c5  mov     r8d, edi; int
0x1800177c8  mov     rcx, r14; wchar_t *
0x1800177cb  call    ?PersistPauseDate@PolicyHelpers@@SAJPEB_WU_FILETIME@@H@Z; PolicyHelpers::PersistPauseDate(wchar_t const *,_FILETIME,int)
0x1800177d0  jmp     short loc_1800177D7
0x1800177d2  mov     eax, 80004003h
0x1800177d7  mov     rcx, [rbp+var_8]
0x1800177db  xor     rcx, rsp; StackCookie
0x1800177de  call    __security_check_cookie
0x1800177e3  lea     r11, [rsp+40h+var_s0]
0x1800177e8  mov     rbx, [r11+38h]
0x1800177ec  mov     rsi, [r11+40h]
0x1800177f0  mov     rsp, r11
0x1800177f3  pop     r15
0x1800177f5  pop     r14
0x1800177f7  pop     r12
0x1800177f9  pop     rdi
0x1800177fa  pop     rbp
0x1800177fb  retn
```
