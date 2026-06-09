# AslLogpWritePanther(_ASL_LOG *,ASL_LOG_LEVEL,char const *,unsigned __int64,char const *,tagLOG_PARTIAL_MSG * (*)(int,ulong,char const *,...),tagLOGRESULT (*)(void *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint))

- ea: `0x14000a058`
- end: `0x14000a15d`
- name: `?AslLogpWritePanther@@YAXPEAU_ASL_LOG@@W4ASL_LOG_LEVEL@@PEBD_K2P6APEAUtagLOG_PARTIAL_MSG@@HK2ZZP6A?AW4tagLOGRESULT@@PEAXK22K225K5I@Z@Z`
- size: `261`
- prototype: `__int64 __fastcall(const char **, int, __int64, int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000b83c`

## callees

- `0x14000adb8`
- `0x14002e420`
- `0x14002f010`

## pseudocode

```c
__int64 __fastcall AslLogpWritePanther(const char **a1, int a2, __int64 a3, int a4, const char *a5)
{
  __int64 (__fastcall *v7)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // rbp
  __int64 (__fastcall *v8)(__int64, __int64, const char *, char *); // rdi
  int v10; // eax
  char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rax
  char v15[1024]; // [rsp+60h] [rbp-438h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))WdsSetupLogMessageA;
  v8 = (__int64 (__fastcall *)(__int64, __int64, const char *, char *))qword_140042B18;
  v10 = RtlStringCchPrintfA(v15, 0x400u, "%hs: %hs", *a1, a5);
  v11 = v15;
  if ( v10 < 0 )
    v11 = (char *)a5;
  v12 = 0x2000000;
  if ( a2 != 1 )
    v12 = 0x4000000;
  v13 = v8(1, v12, "%hs", v11);
  return v7(v13, 671744, "D", 0, a4, a3, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14000a058  mov     [rsp+arg_8], rbx
0x14000a05d  push    rbp
0x14000a05e  push    rsi
0x14000a05f  push    rdi
0x14000a060  push    r14
0x14000a062  push    r15
0x14000a064  sub     rsp, 470h
0x14000a06b  mov     rax, cs:__security_cookie
0x14000a072  xor     rax, rsp
0x14000a075  mov     [rsp+498h+var_38], rax
0x14000a07d  mov     rbx, [rsp+498h+arg_20]
0x14000a085  mov     r15, r9
0x14000a088  mov     r9, [rcx]
0x14000a08b  mov     r14, r8
0x14000a08e  mov     rbp, cs:WdsSetupLogMessageA
0x14000a095  lea     rcx, [rsp+498h+var_438]; char *
0x14000a09a  mov     rdi, cs:qword_140042B18
0x14000a0a1  lea     r8, aHsHs; "%hs: %hs"
0x14000a0a8  mov     esi, edx
0x14000a0aa  mov     [rsp+498h+var_478], rbx
0x14000a0af  mov     edx, 400h; unsigned __int64
0x14000a0b4  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000a0b9  test    eax, eax
0x14000a0bb  lea     r9, [rsp+498h+var_438]
0x14000a0c0  mov     ecx, 1
0x14000a0c5  lea     r8, aHs; "%hs"
0x14000a0cc  cmovs   r9, rbx
0x14000a0d0  mov     edx, 2000000h
0x14000a0d5  cmp     esi, ecx
0x14000a0d7  mov     eax, 4000000h
0x14000a0dc  cmovnz  edx, eax
0x14000a0df  mov     rax, rdi
0x14000a0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0e7  mov     [rsp+498h+var_448], 0
0x14000a0ef  lea     r8, aD_0; "D"
0x14000a0f6  mov     [rsp+498h+var_450], 0
0x14000a0ff  mov     rcx, rax
0x14000a102  mov     [rsp+498h+var_458], 0
0x14000a10a  xor     r9d, r9d
0x14000a10d  mov     [rsp+498h+var_460], 0
0x14000a116  mov     edx, 0A4000h
0x14000a11b  mov     [rsp+498h+var_468], 0
0x14000a124  mov     rax, rbp
0x14000a127  mov     [rsp+498h+var_470], r14
0x14000a12c  mov     dword ptr [rsp+498h+var_478], r15d
0x14000a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a136  mov     rcx, [rsp+498h+var_38]
0x14000a13e  xor     rcx, rsp; StackCookie
0x14000a141  call    __security_check_cookie
0x14000a146  mov     rbx, [rsp+498h+arg_8]
0x14000a14e  add     rsp, 470h
0x14000a155  pop     r15
0x14000a157  pop     r14
0x14000a159  pop     rdi
0x14000a15a  pop     rsi
0x14000a15b  pop     rbp
0x14000a15c  retn
```
