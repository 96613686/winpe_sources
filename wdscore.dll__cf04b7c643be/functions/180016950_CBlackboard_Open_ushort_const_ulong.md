# CBlackboard::Open(ushort const *,ulong)

- ea: `0x180016950`
- end: `0x180016ae0`
- name: `?Open@CBlackboard@@QEAAHPEBGK@Z`
- size: `400`
- prototype: `__int64 __fastcall(CBlackboard *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800107c4`

## callees

- `0x180002250`
- `0x180011578`
- `0x180016950`
- `0x1800174c0`
- `0x18001dc70`
- `0x18002a010`

## string_xrefs

- `0x180016a21`: `CBlackboard::Open`
- `0x180016ab0`: `CBlackboard::Open`
- `0x1800169dd`: `CBlackboard::Open: m_Storage.CreateType(%s) failed.`
- `0x180016a6c`: `CBlackboard::Open: %s succeeded.`

## pseudocode

```c
__int64 __fastcall CBlackboard::Open(CBlackboard *this, const unsigned __int16 *a2, char a3)
{
  int v3; // edi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  void *v9; // r9
  BOOL v10; // eax
  struct CTypeManager *Type; // rax
  int v12; // ebx
  int *v13; // rax
  int v15; // ebx
  int *v16; // rax
  unsigned __int64 v17; // [rsp+20h] [rbp-68h]
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  v3 = a3 & 2;
  if ( (a3 & 1) != 0 && (a3 & 2) != 0 || !(unsigned int)CStorage::Open(this, a2, a3) )
    return 0;
  if ( v3 )
    v10 = 1;
  else
    v10 = *((_DWORD *)this + 12) == 0;
  Type = CStorage::CreateType(this, v7, v8, v9, v17, v10, a3 & 4);
  *((_QWORD *)this + 15) = Type;
  if ( !Type )
  {
    if ( g_bEnableDiagnosticMode )
    {
      v12 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
      v13 = (int *)ConstructPartialMsgW(
                     0x6B000000u,
                     "CBlackboard::Open: m_Storage.CreateType(%s) failed.",
                     (const char *)a2);
      WdsSetupLogMessageW(
        v13,
        589824,
        (__int64)L"D",
        0,
        0x1352u,
        L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
        L"CBlackboard::Open",
        lpModuleName,
        v12,
        0,
        0);
    }
    return 0;
  }
  v15 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
  v16 = (int *)ConstructPartialMsgW(0x4000008u, "CBlackboard::Open: %s succeeded.", (const char *)a2);
  WdsSetupLogMessageW(
    v16,
    589824,
    (__int64)L"D",
    0,
    0x1356u,
    L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
    L"CBlackboard::Open",
    lpModuleName,
    v15,
    0,
    0);
  return 1;
}

```

## disassembly

```asm
0x180016950  push    rbx
0x180016952  push    rbp
0x180016953  push    rsi
0x180016954  push    rdi
0x180016955  push    r15
0x180016957  sub     rsp, 60h
0x18001695b  mov     edi, r8d
0x18001695e  mov     r15d, 1
0x180016964  and     edi, 2
0x180016967  mov     ebx, r8d
0x18001696a  mov     rbp, rdx
0x18001696d  mov     rsi, rcx
0x180016970  test    r15b, r8b
0x180016973  jz      short loc_18001697D
0x180016975  test    edi, edi
0x180016977  jnz     loc_180016A49
0x18001697d  call    ?Open@CStorage@@QEAAHPEBGK@Z; CStorage::Open(ushort const *,ulong)
0x180016982  test    eax, eax
0x180016984  jz      loc_180016A49
0x18001698a  test    edi, edi
0x18001698c  jz      short loc_180016993
0x18001698e  mov     eax, r15d
0x180016991  jmp     short loc_18001699C
0x180016993  xor     eax, eax
0x180016995  cmp     [rsi+30h], eax
0x180016998  cmovz   eax, r15d
0x18001699c  and     ebx, 4
0x18001699f  mov     rcx, rsi; this
0x1800169a2  mov     dword ptr [rsp+88h+var_58], ebx; int
0x1800169a6  mov     dword ptr [rsp+88h+var_60], eax; int
0x1800169aa  call    ?CreateType@CStorage@@QEAAPEAVCTypeManager@@_K0PEAX0HH@Z; CStorage::CreateType(unsigned __int64,unsigned __int64,void *,unsigned __int64,int,int)
0x1800169af  mov     [rsi+78h], rax
0x1800169b3  test    rax, rax
0x1800169b6  jnz     loc_180016A57
0x1800169bc  cmp     cs:?g_bEnableDiagnosticMode@@3HA, eax; int g_bEnableDiagnosticMode
0x1800169c2  jz      loc_180016A49
0x1800169c8  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800169cf  mov     rax, [rcx]
0x1800169d2  mov     rax, [rax]
0x1800169d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169da  mov     r8, rbp
0x1800169dd  lea     rdx, aCblackboardOpe_1; "CBlackboard::Open: m_Storage.CreateType"...
0x1800169e4  mov     ecx, 6B000000h; unsigned int
0x1800169e9  mov     ebx, eax
0x1800169eb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800169f0  mov     rcx, [rsp+88h]
0x1800169f8  lea     r8, aD_1; "D"
0x1800169ff  mov     [rsp+88h+var_38], 0; int
0x180016a07  xor     r9d, r9d; int
0x180016a0a  mov     [rsp+88h+var_40], 0; __int64
0x180016a13  mov     edx, 90000h; int
0x180016a18  mov     [rsp+88h+var_48], ebx; int
0x180016a1c  mov     [rsp+88h+lpModuleName], rcx; lpModuleName
0x180016a21  lea     rcx, aCblackboardOpe_0; "CBlackboard::Open"
0x180016a28  mov     [rsp+88h+var_58], rcx; __int64
0x180016a2d  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x180016a34  mov     [rsp+88h+var_60], rcx; unsigned __int16 *
0x180016a39  mov     rcx, rax; int
0x180016a3c  mov     dword ptr [rsp+88h+var_68], 1352h; int
0x180016a44  call    WdsSetupLogMessageW
0x180016a49  xor     eax, eax
0x180016a4b  add     rsp, 60h
0x180016a4f  pop     r15
0x180016a51  pop     rdi
0x180016a52  pop     rsi
0x180016a53  pop     rbp
0x180016a54  pop     rbx
0x180016a55  retn
0x180016a57  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016a5e  mov     rax, [rcx]
0x180016a61  mov     rax, [rax]
0x180016a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a69  mov     r8, rbp
0x180016a6c  lea     rdx, aCblackboardOpe; "CBlackboard::Open: %s succeeded."
0x180016a73  mov     ecx, 4000008h; unsigned int
0x180016a78  mov     ebx, eax
0x180016a7a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016a7f  mov     rcx, [rsp+88h]
0x180016a87  lea     r8, aD_1; "D"
0x180016a8e  mov     [rsp+88h+var_38], 0; int
0x180016a96  xor     r9d, r9d; int
0x180016a99  mov     [rsp+88h+var_40], 0; __int64
0x180016aa2  mov     edx, 90000h; int
0x180016aa7  mov     [rsp+88h+var_48], ebx; int
0x180016aab  mov     [rsp+88h+lpModuleName], rcx; lpModuleName
0x180016ab0  lea     rcx, aCblackboardOpe_0; "CBlackboard::Open"
0x180016ab7  mov     [rsp+88h+var_58], rcx; __int64
0x180016abc  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x180016ac3  mov     [rsp+88h+var_60], rcx; unsigned __int16 *
0x180016ac8  mov     rcx, rax; int
0x180016acb  mov     dword ptr [rsp+88h+var_68], 1356h; int
0x180016ad3  call    WdsSetupLogMessageW
0x180016ad8  mov     eax, r15d
0x180016adb  jmp     loc_180016A4B
```
