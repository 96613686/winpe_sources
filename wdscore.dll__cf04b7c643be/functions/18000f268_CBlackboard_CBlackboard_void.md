# CBlackboard::~CBlackboard(void)

- ea: `0x18000f268`
- end: `0x18000f343`
- name: `??1CBlackboard@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(CBlackboard *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000f568`

## callees

- `0x180002250`
- `0x18000f268`
- `0x18000f4ec`
- `0x1800101dc`
- `0x18001dc70`
- `0x18002a010`

## string_xrefs

- `0x18000f2c0`: `CBlackboard::m_lAccessSpinLock = %d for BB="%s"`

## pseudocode

```c
void __fastcall CBlackboard::~CBlackboard(CBlackboard *this)
{
  int v2; // edi
  const char *v3; // r9
  int *v4; // rax
  LPCWSTR lpModuleName; // [rsp+78h] [rbp+0h]

  if ( *((_DWORD *)this + 32) )
  {
    v2 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
    if ( *((_QWORD *)this + 2) )
      v3 = (const char *)*((_QWORD *)this + 1);
    else
      v3 = 0;
    v4 = (int *)ConstructPartialMsgW(
                  0x3000007u,
                  "CBlackboard::m_lAccessSpinLock = %d for BB=\"%s\"",
                  *((_DWORD *)this + 32),
                  v3);
    WdsSetupLogMessageW(
      v4,
      589824,
      (__int64)L"D",
      0,
      0x1329u,
      L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
      L"CBlackboard::~CBlackboard",
      lpModuleName,
      v2,
      0,
      0);
  }
  CBlackboard::Close(this);
  CStorage::~CStorage(this);
}

```

## disassembly

```asm
0x18000f268  mov     rax, rsp
0x18000f26b  push    rdi
0x18000f26c  sub     rsp, 70h
0x18000f270  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000f278  mov     [rax+8], rbx
0x18000f27c  mov     [rax+10h], rsi
0x18000f280  mov     rbx, rcx
0x18000f283  cmp     dword ptr [rcx+80h], 0
0x18000f28a  jz      loc_18000F322
0x18000f290  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f297  mov     rax, [rcx]
0x18000f29a  mov     rax, [rax]
0x18000f29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2a2  mov     edi, eax
0x18000f2a4  mov     rsi, [rsp+78h]
0x18000f2a9  cmp     qword ptr [rbx+10h], 0
0x18000f2ae  jnz     short loc_18000F2B5
0x18000f2b0  xor     r9d, r9d
0x18000f2b3  jmp     short loc_18000F2B9
0x18000f2b5  mov     r9, [rbx+8]
0x18000f2b9  mov     r8d, [rbx+80h]
0x18000f2c0  lea     rdx, aCblackboardMLa; "CBlackboard::m_lAccessSpinLock = %d for"...
0x18000f2c7  mov     ecx, 3000007h; unsigned int
0x18000f2cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f2d1  mov     [rsp+78h+var_28], 0; int
0x18000f2d9  mov     [rsp+78h+var_30], 0; __int64
0x18000f2e2  mov     [rsp+78h+var_38], edi; int
0x18000f2e6  mov     [rsp+78h+lpModuleName], rsi; lpModuleName
0x18000f2eb  lea     rcx, aCblackboardCbl; "CBlackboard::~CBlackboard"
0x18000f2f2  mov     [rsp+78h+var_48], rcx; __int64
0x18000f2f7  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000f2fe  mov     [rsp+78h+var_50], rcx; unsigned __int16 *
0x18000f303  mov     [rsp+78h+var_58], 1329h; int
0x18000f30b  xor     r9d, r9d; int
0x18000f30e  lea     r8, aD_1; "D"
0x18000f315  mov     edx, 90000h; int
0x18000f31a  mov     rcx, rax; int
0x18000f31d  call    WdsSetupLogMessageW
0x18000f322  mov     rcx, rbx; this
0x18000f325  call    ?Close@CBlackboard@@QEAAHXZ; CBlackboard::Close(void)
0x18000f32a  mov     rcx, rbx; this
0x18000f32d  lea     r11, [rsp+78h+var_8]
0x18000f332  mov     rbx, [r11+10h]
0x18000f336  mov     rsi, [r11+18h]
0x18000f33a  mov     rsp, r11
0x18000f33d  pop     rdi
0x18000f33e  jmp     ??1CStorage@@QEAA@XZ; CStorage::~CStorage(void)
```
