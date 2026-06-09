# CSpinLockFileMappingArray::Create(ushort const *,CObjectName &,unsigned __int64,int)

- ea: `0x180010ca4`
- end: `0x180010e3b`
- name: `?Create@CSpinLockFileMappingArray@@QEAAHPEBGAEAVCObjectName@@_KH@Z`
- size: `407`
- prototype: `__int64 __fastcall(CSpinLockFileMappingArray *__hidden this, const unsigned __int16 *, struct CObjectName *, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, installer_update`

## callers

- `0x180017598`

## callees

- `0x180002250`
- `0x180010ca4`
- `0x1800114e4`
- `0x18001dc70`
- `0x18002a010`

## string_xrefs

- `0x180010dc6`: `CSpinLockFileMappingArray::Create`
- `0x180010d82`: `CSpinLockFileMappingArray::Create: m_pMapping->Create(%s) failed.`

## pseudocode

```c
__int64 __fastcall CSpinLockFileMappingArray::Create(
        CSpinLockFileMappingArray *this,
        const char *a2,
        struct CObjectName *a3,
        __int64 a4,
        int a5)
{
  struct CConsistentMapping *Object; // rax
  int v11; // ebx
  int *v12; // rax
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]
  int v14; // [rsp+90h] [rbp+8h] BYREF

  v14 = 0;
  Object = CConsistentMappingFactory::CreateObject(a5);
  *(_QWORD *)this = Object;
  if ( !Object )
    return 0;
  if ( (*(unsigned int (__fastcall **)(struct IKernel32Interface *, const char *))(*(_QWORD *)g_Kernel32 + 288LL))(
         g_Kernel32,
         a2) != -1 )
    (*(void (__fastcall **)(struct IKernel32Interface *, const char *))(*(_QWORD *)g_Kernel32 + 264LL))(g_Kernel32, a2);
  if ( !(*(unsigned int (__fastcall **)(_QWORD, const char *, struct CObjectName *, __int64, _DWORD, int, __int64, int *, _DWORD))(**(_QWORD **)this + 32LL))(
          *(_QWORD *)this,
          a2,
          a3,
          1,
          0,
          1,
          a4,
          &v14,
          0) )
  {
    if ( g_bEnableDiagnosticMode )
    {
      v11 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
      v12 = (int *)ConstructPartialMsgW(
                     0x6B000000u,
                     "CSpinLockFileMappingArray::Create: m_pMapping->Create(%s) failed.",
                     a2);
      WdsSetupLogMessageW(
        v12,
        589824,
        (__int64)L"D",
        0,
        0x51Cu,
        L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
        L"CSpinLockFileMappingArray::Create",
        lpModuleName,
        v11,
        0,
        0);
    }
    if ( *(_QWORD *)this )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, 1);
    *(_QWORD *)this = 0;
    return 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 40LL))(*(_QWORD *)this);
  return 1;
}

```

## disassembly

```asm
0x180010ca4  mov     rax, rsp
0x180010ca7  push    rbx
0x180010ca8  push    rbp
0x180010ca9  push    rsi
0x180010caa  push    rdi
0x180010cab  sub     rsp, 68h
0x180010caf  mov     rdi, rcx
0x180010cb2  mov     dword ptr [rax+8], 0
0x180010cb9  mov     ecx, [rsp+88h+arg_20]; int
0x180010cc0  mov     rbx, r9
0x180010cc3  mov     rbp, r8
0x180010cc6  mov     rsi, rdx
0x180010cc9  call    ?CreateObject@CConsistentMappingFactory@@SAPEAVCConsistentMapping@@H@Z; CConsistentMappingFactory::CreateObject(int)
0x180010cce  mov     [rdi], rax
0x180010cd1  test    rax, rax
0x180010cd4  jnz     short loc_180010CDD
0x180010cd6  xor     eax, eax
0x180010cd8  jmp     loc_180010E31
0x180010cdd  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180010ce4  mov     rdx, rsi
0x180010ce7  mov     rax, [rcx]
0x180010cea  mov     rax, [rax+120h]
0x180010cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf6  cmp     eax, 0FFFFFFFFh
0x180010cf9  jz      short loc_180010D14
0x180010cfb  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180010d02  mov     rdx, rsi
0x180010d05  mov     rax, [rcx]
0x180010d08  mov     rax, [rax+108h]
0x180010d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d14  mov     rcx, [rdi]
0x180010d17  lea     rdx, [rsp+88h+arg_0]
0x180010d1f  mov     [rsp+88h+var_48], 0
0x180010d27  mov     r9d, 1
0x180010d2d  mov     [rsp+88h+lpModuleName], rdx
0x180010d32  mov     r8, rbp
0x180010d35  mov     [rsp+88h+var_58], rbx
0x180010d3a  mov     rdx, rsi
0x180010d3d  mov     rax, [rcx]
0x180010d40  mov     dword ptr [rsp+88h+var_60], 1
0x180010d48  mov     [rsp+88h+var_68], 0
0x180010d50  mov     rax, [rax+20h]
0x180010d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d59  test    eax, eax
0x180010d5b  jnz     loc_180010E13
0x180010d61  cmp     cs:?g_bEnableDiagnosticMode@@3HA, eax; int g_bEnableDiagnosticMode
0x180010d67  jz      loc_180010DEE
0x180010d6d  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180010d74  mov     rax, [rcx]
0x180010d77  mov     rax, [rax]
0x180010d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d7f  mov     r8, rsi
0x180010d82  lea     rdx, aCspinlockfilem_0; "CSpinLockFileMappingArray::Create: m_pM"...
0x180010d89  mov     ecx, 6B000000h; unsigned int
0x180010d8e  mov     ebx, eax
0x180010d90  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180010d95  mov     rcx, [rsp+88h]
0x180010d9d  lea     r8, aD_1; "D"
0x180010da4  mov     [rsp+88h+var_38], 0; int
0x180010dac  xor     r9d, r9d; int
0x180010daf  mov     [rsp+88h+var_40], 0; __int64
0x180010db8  mov     edx, 90000h; int
0x180010dbd  mov     [rsp+88h+var_48], ebx; int
0x180010dc1  mov     [rsp+88h+lpModuleName], rcx; lpModuleName
0x180010dc6  lea     rcx, aCspinlockfilem; "CSpinLockFileMappingArray::Create"
0x180010dcd  mov     [rsp+88h+var_58], rcx; __int64
0x180010dd2  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x180010dd9  mov     [rsp+88h+var_60], rcx; unsigned __int16 *
0x180010dde  mov     rcx, rax; int
0x180010de1  mov     [rsp+88h+var_68], 51Ch; int
0x180010de9  call    WdsSetupLogMessageW
0x180010dee  mov     rcx, [rdi]
0x180010df1  test    rcx, rcx
0x180010df4  jz      short loc_180010E07
0x180010df6  mov     rax, [rcx]
0x180010df9  mov     edx, 1
0x180010dfe  mov     rax, [rax+8]
0x180010e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e07  mov     qword ptr [rdi], 0
0x180010e0e  jmp     loc_180010CD6
0x180010e13  cmp     [rsp+88h+arg_0], 0
0x180010e1b  jz      short loc_180010E2C
0x180010e1d  mov     rcx, [rdi]
0x180010e20  mov     rax, [rcx]
0x180010e23  mov     rax, [rax+28h]
0x180010e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2c  mov     eax, 1
0x180010e31  add     rsp, 68h
0x180010e35  pop     rdi
0x180010e36  pop     rsi
0x180010e37  pop     rbp
0x180010e38  pop     rbx
0x180010e39  retn
```
