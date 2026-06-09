# CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)

- ea: `0x180001338`
- end: `0x1800013e6`
- name: `??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ`
- size: `174`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800010f0`
- `0x180001180`
- `0x1800011e0`
- `0x180001240`
- `0x1800012a0`

## callees

- `0x180001338`
- `0x1800013e8`
- `0x180001b30`
- `0x180002202`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x1800013c7`
- `KERNEL32!OutputDebugStringA` at `0x1800013c7`
- `KERNEL32!LeaveCriticalSection` at `0x180001368`
- `KERNEL32!LeaveCriticalSection` at `0x180001368`

## pseudocode

```c
void __fastcall CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(__int64 a1)
{
  int v1; // eax
  int v3; // eax
  CHAR OutputString[256]; // [rsp+40h] [rbp-118h] BYREF

  v1 = *(_DWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 - 1;
    *(_DWORD *)(a1 + 8) = v3;
    if ( !v3 )
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
  }
  if ( *(_DWORD *)(a1 + 8) )
  {
    memset_0(OutputString, 0, sizeof(OutputString));
    StringCchPrintfA(
      OutputString,
      0x100u,
      "%s[%s:%u] %s\n",
      "RETAIL ASSERT",
      "internal\\base\\private\\inc\\eco\\wds\\locks.h",
      362,
      "m_uLockCount == 0");
    OutputDebugStringA(OutputString);
  }
}

```

## disassembly

```asm
0x180001338  push    rbx
0x18000133a  sub     rsp, 150h
0x180001341  mov     rax, cs:__security_cookie
0x180001348  xor     rax, rsp
0x18000134b  mov     [rsp+158h+var_18], rax
0x180001353  mov     eax, [rcx+8]
0x180001356  mov     rbx, rcx
0x180001359  test    eax, eax
0x18000135b  jz      short loc_18000136E
0x18000135d  sub     eax, 1
0x180001360  mov     [rcx+8], eax
0x180001363  jnz     short loc_18000136E
0x180001365  mov     rcx, [rcx]; lpCriticalSection
0x180001368  call    cs:__imp_LeaveCriticalSection
0x18000136e  cmp     dword ptr [rbx+8], 0
0x180001372  jz      short loc_1800013CD
0x180001374  mov     ebx, 100h
0x180001379  lea     rcx, [rsp+158h+OutputString]; void *
0x18000137e  mov     r8d, ebx; Size
0x180001381  xor     edx, edx; Val
0x180001383  call    memset_0
0x180001388  lea     rax, aMUlockcount0; "m_uLockCount == 0"
0x18000138f  mov     edx, ebx; unsigned __int64
0x180001391  mov     [rsp+158h+var_128], rax
0x180001396  lea     r9, aRetailAssert; "RETAIL ASSERT"
0x18000139d  lea     rax, aInternalBasePr; "internal\\base\\private\\inc\\eco\\wds"...
0x1800013a4  mov     [rsp+158h+var_130], 16Ah
0x1800013ac  lea     r8, aSSUS; "%s[%s:%u] %s\n"
0x1800013b3  mov     [rsp+158h+var_138], rax
0x1800013b8  lea     rcx, [rsp+158h+OutputString]; Buffer
0x1800013bd  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800013c2  lea     rcx, [rsp+158h+OutputString]; lpOutputString
0x1800013c7  call    cs:__imp_OutputDebugStringA
0x1800013cd  mov     rcx, [rsp+158h+var_18]
0x1800013d5  xor     rcx, rsp; StackCookie
0x1800013d8  call    __security_check_cookie
0x1800013dd  add     rsp, 150h
0x1800013e4  pop     rbx
0x1800013e5  retn
```
