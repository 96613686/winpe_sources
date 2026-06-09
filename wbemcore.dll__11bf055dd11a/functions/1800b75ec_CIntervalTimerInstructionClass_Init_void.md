# CIntervalTimerInstructionClass::Init(void)

- ea: `0x1800b75ec`
- end: `0x1800b7997`
- name: `?Init@CIntervalTimerInstructionClass@@QEAAXXZ`
- size: `939`
- prototype: `void __fastcall(CIntervalTimerInstructionClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b75ec`
- `0x1800badac`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b77f2`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b77f2`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b76ba`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b789f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b76ba`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b789f`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b7757`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b7757`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b774b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b774b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7940`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b794c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7958`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7963`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7940`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b794c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7958`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7963`
- `wbemcomn!GetMemLogObject` at `0x1800b7649`
- `wbemcomn!GetMemLogObject` at `0x1800b76e5`
- `wbemcomn!GetMemLogObject` at `0x1800b7785`
- `wbemcomn!GetMemLogObject` at `0x1800b782d`
- `wbemcomn!GetMemLogObject` at `0x1800b78da`
- `wbemcomn!GetMemLogObject` at `0x1800b7649`
- `wbemcomn!GetMemLogObject` at `0x1800b76e5`
- `wbemcomn!GetMemLogObject` at `0x1800b7785`
- `wbemcomn!GetMemLogObject` at `0x1800b782d`
- `wbemcomn!GetMemLogObject` at `0x1800b78da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b76f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7793`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b783b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b78e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b76f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7793`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b783b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b78e8`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b763a`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b763a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CIntervalTimerInstructionClass::Init(CIntervalTimerInstructionClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v11[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v12[864]; // [rsp+C0h] [rbp-40h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v12);
  CTimerInstructionClass::Init((CTimerInstructionClass *)v12);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v12, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        317,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"__IntervalTimerInstruction");
  if ( (*(unsigned int (__fastcall **)(CIntervalTimerInstructionClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v11,
         0) == -2147217402 )
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        318,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8);
  CVar::SetAsNull((CVar *)v8);
  if ( (*(unsigned int (__fastcall **)(CIntervalTimerInstructionClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"IntervalBetweenEvents",
         v8,
         19) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        319,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CIntervalTimerInstructionClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"IntervalBetweenEvents",
         L"not_null",
         19,
         v10) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        320,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"milliseconds");
  if ( (*(unsigned int (__fastcall **)(CIntervalTimerInstructionClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"IntervalBetweenEvents",
         L"units",
         19,
         v9) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        321,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v11);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v12);
}

```

## disassembly

```asm
0x1800b75ec  mov     [rsp-8+arg_8], rbx
0x1800b75f1  mov     [rsp-8+arg_10], rdi
0x1800b75f6  push    rbp
0x1800b75f7  lea     rbp, [rsp-330h]
0x1800b75ff  sub     rsp, 430h
0x1800b7606  mov     rax, cs:__security_cookie
0x1800b760d  xor     rax, rsp
0x1800b7610  mov     [rbp+330h+var_10], rax
0x1800b7617  mov     rbx, rcx
0x1800b761a  lea     rcx, [rbp+330h+var_370]; this
0x1800b761e  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b7623  nop
0x1800b7624  lea     rcx, [rbp+330h+var_370]; this
0x1800b7628  call    ?Init@CTimerInstructionClass@@QEAAXXZ; CTimerInstructionClass::Init(void)
0x1800b762d  xor     r9d, r9d
0x1800b7630  xor     r8d, r8d
0x1800b7633  lea     rdx, [rbp+330h+var_370]
0x1800b7637  mov     rcx, rbx
0x1800b763a  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b7640  mov     edi, 80041006h
0x1800b7645  cmp     eax, edi
0x1800b7647  jnz     short loc_1800B76AA
0x1800b7649  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b764f  mov     edx, 0FFFFFFFEh
0x1800b7654  mov     rcx, rax
0x1800b7657  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b765d  lea     rax, WPP_GLOBAL_Control
0x1800b7664  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b766b  cmp     rcx, rax
0x1800b766e  jz      short loc_1800B7698
0x1800b7670  test    byte ptr [rcx+1Ch], 1
0x1800b7674  jz      short loc_1800B7698
0x1800b7676  cmp     byte ptr [rcx+19h], 2
0x1800b767a  jb      short loc_1800B7698
0x1800b767c  mov     edx, 13Dh
0x1800b7681  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7688  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b768f  mov     rcx, [rcx+10h]
0x1800b7693  call    WPP_SF_s
0x1800b7698  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b769f  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b76a4  call    _CxxThrowException_0
0x1800b76aa  lea     r8, aIntervaltimeri; "__IntervalTimerInstruction"
0x1800b76b1  mov     edx, 8
0x1800b76b6  lea     rcx, [rbp+330h+var_398]
0x1800b76ba  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b76c0  nop
0x1800b76c1  mov     rax, [rbx]
0x1800b76c4  xor     r9d, r9d
0x1800b76c7  lea     r8, [rbp+330h+var_398]
0x1800b76cb  lea     rdx, aClass_0; "__CLASS"
0x1800b76d2  mov     rcx, rbx
0x1800b76d5  mov     rax, [rax+368h]
0x1800b76dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b76e1  cmp     eax, edi
0x1800b76e3  jnz     short loc_1800B7746
0x1800b76e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b76eb  mov     edx, 0FFFFFFFEh
0x1800b76f0  mov     rcx, rax
0x1800b76f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b76f9  lea     rax, WPP_GLOBAL_Control
0x1800b7700  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7707  cmp     rcx, rax
0x1800b770a  jz      short loc_1800B7734
0x1800b770c  test    byte ptr [rcx+1Ch], 1
0x1800b7710  jz      short loc_1800B7734
0x1800b7712  cmp     byte ptr [rcx+19h], 2
0x1800b7716  jb      short loc_1800B7734
0x1800b7718  mov     edx, 13Eh
0x1800b771d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7724  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b772b  mov     rcx, [rcx+10h]
0x1800b772f  call    WPP_SF_s
0x1800b7734  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b773b  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7740  call    _CxxThrowException_0
0x1800b7746  lea     rcx, [rsp+430h+var_3F8]
0x1800b774b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b7751  nop
0x1800b7752  lea     rcx, [rsp+430h+var_3F8]
0x1800b7757  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b775d  mov     rax, [rbx]
0x1800b7760  mov     r9d, 13h
0x1800b7766  lea     r8, [rsp+430h+var_3F8]
0x1800b776b  lea     rdx, aIntervalbetwee; "IntervalBetweenEvents"
0x1800b7772  mov     rcx, rbx
0x1800b7775  mov     rax, [rax+368h]
0x1800b777c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7781  cmp     eax, edi
0x1800b7783  jnz     short loc_1800B77E6
0x1800b7785  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b778b  mov     edx, 0FFFFFFFEh
0x1800b7790  mov     rcx, rax
0x1800b7793  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7799  lea     rax, WPP_GLOBAL_Control
0x1800b77a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b77a7  cmp     rcx, rax
0x1800b77aa  jz      short loc_1800B77D4
0x1800b77ac  test    byte ptr [rcx+1Ch], 1
0x1800b77b0  jz      short loc_1800B77D4
0x1800b77b2  cmp     byte ptr [rcx+19h], 2
0x1800b77b6  jb      short loc_1800B77D4
0x1800b77b8  mov     edx, 13Fh
0x1800b77bd  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b77c4  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b77cb  mov     rcx, [rcx+10h]
0x1800b77cf  call    WPP_SF_s
0x1800b77d4  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b77db  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b77e0  call    _CxxThrowException_0
0x1800b77e6  or      edx, 0FFFFFFFFh
0x1800b77e9  lea     r8d, [rdx+0Ch]
0x1800b77ed  lea     rcx, [rsp+430h+var_3B8]
0x1800b77f2  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b77f8  nop
0x1800b77f9  mov     rax, [rbx]
0x1800b77fc  lea     rcx, [rsp+430h+var_3B8]
0x1800b7801  mov     [rsp+430h+var_410], rcx
0x1800b7806  mov     r9d, 13h
0x1800b780c  lea     r8, aNotNull; "not_null"
0x1800b7813  lea     rdx, aIntervalbetwee; "IntervalBetweenEvents"
0x1800b781a  mov     rcx, rbx
0x1800b781d  mov     rax, [rax+378h]
0x1800b7824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7829  cmp     eax, edi
0x1800b782b  jnz     short loc_1800B788E
0x1800b782d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7833  mov     edx, 0FFFFFFFEh
0x1800b7838  mov     rcx, rax
0x1800b783b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7841  lea     rax, WPP_GLOBAL_Control
0x1800b7848  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b784f  cmp     rcx, rax
0x1800b7852  jz      short loc_1800B787C
0x1800b7854  test    byte ptr [rcx+1Ch], 1
0x1800b7858  jz      short loc_1800B787C
0x1800b785a  cmp     byte ptr [rcx+19h], 2
0x1800b785e  jb      short loc_1800B787C
0x1800b7860  mov     edx, 140h
0x1800b7865  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b786c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7873  mov     rcx, [rcx+10h]
0x1800b7877  call    WPP_SF_s
0x1800b787c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7883  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7888  call    _CxxThrowException_0
0x1800b788e  lea     r8, aMilliseconds; "milliseconds"
0x1800b7895  mov     edx, 8
0x1800b789a  lea     rcx, [rsp+430h+var_3D8]
0x1800b789f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b78a5  nop
0x1800b78a6  mov     rax, [rbx]
0x1800b78a9  lea     rcx, [rsp+430h+var_3D8]
0x1800b78ae  mov     [rsp+430h+var_410], rcx
0x1800b78b3  mov     r9d, 13h
0x1800b78b9  lea     r8, aUnits; "units"
0x1800b78c0  lea     rdx, aIntervalbetwee; "IntervalBetweenEvents"
0x1800b78c7  mov     rcx, rbx
0x1800b78ca  mov     rax, [rax+378h]
0x1800b78d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b78d6  cmp     eax, edi
0x1800b78d8  jnz     short loc_1800B793B
0x1800b78da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b78e0  mov     edx, 0FFFFFFFEh
0x1800b78e5  mov     rcx, rax
0x1800b78e8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b78ee  lea     rax, WPP_GLOBAL_Control
0x1800b78f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b78fc  cmp     rcx, rax
0x1800b78ff  jz      short loc_1800B7929
0x1800b7901  test    byte ptr [rcx+1Ch], 1
0x1800b7905  jz      short loc_1800B7929
0x1800b7907  cmp     byte ptr [rcx+19h], 2
0x1800b790b  jb      short loc_1800B7929
0x1800b790d  mov     edx, 141h
0x1800b7912  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7919  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7920  mov     rcx, [rcx+10h]
0x1800b7924  call    WPP_SF_s
0x1800b7929  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7930  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7935  call    _CxxThrowException_0
0x1800b793b  lea     rcx, [rsp+430h+var_3D8]
0x1800b7940  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7946  nop
0x1800b7947  lea     rcx, [rsp+430h+var_3B8]
0x1800b794c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7952  nop
0x1800b7953  lea     rcx, [rsp+430h+var_3F8]
0x1800b7958  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b795e  nop
0x1800b795f  lea     rcx, [rbp+330h+var_398]
0x1800b7963  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7969  nop
0x1800b796a  lea     rcx, [rbp+330h+var_370]; this
0x1800b796e  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b7973  mov     rcx, [rbp+330h+var_10]
0x1800b797a  xor     rcx, rsp; StackCookie
0x1800b797d  call    __security_check_cookie
0x1800b7982  lea     r11, [rsp+430h+var_s0]
0x1800b798a  mov     rbx, [r11+18h]
0x1800b798e  mov     rdi, [r11+20h]
0x1800b7992  mov     rsp, r11
0x1800b7995  pop     rbp
0x1800b7996  retn
```
