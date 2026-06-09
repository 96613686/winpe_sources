# CTimerInstructionClass::Init(void)

- ea: `0x1800badac`
- end: `0x1800bb1e4`
- name: `?Init@CTimerInstructionClass@@QEAAXXZ`
- size: `1080`
- prototype: `void __fastcall(CTimerInstructionClass *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x1800b2624`
- `0x1800b75ec`

## callees

- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b6670`
- `0x1800badac`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bafb0`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb04b`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb0f0`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bafb0`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb04b`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb0f0`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bae7a`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bae7a`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800baf17`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800baf17`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800baf0b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800baf0b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb182`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb18e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb199`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb1a5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb1b0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb182`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb18e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb199`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb1a5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb1b0`
- `wbemcomn!GetMemLogObject` at `0x1800bae09`
- `wbemcomn!GetMemLogObject` at `0x1800baea5`
- `wbemcomn!GetMemLogObject` at `0x1800baf45`
- `wbemcomn!GetMemLogObject` at `0x1800bafde`
- `wbemcomn!GetMemLogObject` at `0x1800bb083`
- `wbemcomn!GetMemLogObject` at `0x1800bb11c`
- `wbemcomn!GetMemLogObject` at `0x1800bae09`
- `wbemcomn!GetMemLogObject` at `0x1800baea5`
- `wbemcomn!GetMemLogObject` at `0x1800baf45`
- `wbemcomn!GetMemLogObject` at `0x1800bafde`
- `wbemcomn!GetMemLogObject` at `0x1800bb083`
- `wbemcomn!GetMemLogObject` at `0x1800bb11c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bae17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800baeb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800baf53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bafec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb091`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb12a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bae17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800baeb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800baf53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bafec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb091`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb12a`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800badfa`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800badfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CTimerInstructionClass::Init(CTimerInstructionClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v12[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v13[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v14[864]; // [rsp+E0h] [rbp-20h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v14);
  CEventGeneratorClass::Init((CEventGeneratorClass *)v14);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v14, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        307,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v13, 8, L"__TimerInstruction");
  if ( (*(unsigned int (__fastcall **)(CTimerInstructionClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v13,
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
        308,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9);
  CVar::SetAsNull((CVar *)v9);
  if ( (*(unsigned int (__fastcall **)(CTimerInstructionClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"TimerId",
         v9,
         8) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        309,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v12, 0, 11);
  if ( (*(unsigned int (__fastcall **)(CTimerInstructionClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"SkipIfPassed",
         v12,
         11) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        310,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CTimerInstructionClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"TimerId",
         L"key",
         0,
         v11) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        311,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CTimerInstructionClass *, const wchar_t *, _BYTE *, _QWORD))(*(_QWORD *)this
                                                                                                  + 984LL))(
         this,
         L"abstract",
         v10,
         0) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        312,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v11);
  CVar::~CVar((CVar *)v12);
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v13);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v14);
}

```

## disassembly

```asm
0x1800badac  mov     [rsp-8+arg_8], rbx
0x1800badb1  mov     [rsp-8+arg_10], rdi
0x1800badb6  push    rbp
0x1800badb7  lea     rbp, [rsp-350h]
0x1800badbf  sub     rsp, 450h
0x1800badc6  mov     rax, cs:__security_cookie
0x1800badcd  xor     rax, rsp
0x1800badd0  mov     [rbp+350h+var_10], rax
0x1800badd7  mov     rbx, rcx
0x1800badda  lea     rcx, [rbp+350h+var_370]; this
0x1800badde  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800bade3  nop
0x1800bade4  lea     rcx, [rbp+350h+var_370]; this
0x1800bade8  call    ?Init@CEventGeneratorClass@@QEAAXXZ; CEventGeneratorClass::Init(void)
0x1800baded  xor     r9d, r9d
0x1800badf0  xor     r8d, r8d
0x1800badf3  lea     rdx, [rbp+350h+var_370]
0x1800badf7  mov     rcx, rbx
0x1800badfa  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800bae00  mov     edi, 80041006h
0x1800bae05  cmp     eax, edi
0x1800bae07  jnz     short loc_1800BAE6A
0x1800bae09  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bae0f  mov     edx, 0FFFFFFFEh
0x1800bae14  mov     rcx, rax
0x1800bae17  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bae1d  lea     rax, WPP_GLOBAL_Control
0x1800bae24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bae2b  cmp     rcx, rax
0x1800bae2e  jz      short loc_1800BAE58
0x1800bae30  test    byte ptr [rcx+1Ch], 1
0x1800bae34  jz      short loc_1800BAE58
0x1800bae36  cmp     byte ptr [rcx+19h], 2
0x1800bae3a  jb      short loc_1800BAE58
0x1800bae3c  mov     edx, 133h
0x1800bae41  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bae48  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bae4f  mov     rcx, [rcx+10h]
0x1800bae53  call    WPP_SF_s
0x1800bae58  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bae5f  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800bae64  call    _CxxThrowException_0
0x1800bae6a  lea     r8, aTimerinstructi; "__TimerInstruction"
0x1800bae71  mov     edx, 8
0x1800bae76  lea     rcx, [rbp+350h+var_398]
0x1800bae7a  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bae80  nop
0x1800bae81  mov     rax, [rbx]
0x1800bae84  xor     r9d, r9d
0x1800bae87  lea     r8, [rbp+350h+var_398]
0x1800bae8b  lea     rdx, aClass_0; "__CLASS"
0x1800bae92  mov     rcx, rbx
0x1800bae95  mov     rax, [rax+368h]
0x1800bae9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baea1  cmp     eax, edi
0x1800baea3  jnz     short loc_1800BAF06
0x1800baea5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800baeab  mov     edx, 0FFFFFFFEh
0x1800baeb0  mov     rcx, rax
0x1800baeb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800baeb9  lea     rax, WPP_GLOBAL_Control
0x1800baec0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baec7  cmp     rcx, rax
0x1800baeca  jz      short loc_1800BAEF4
0x1800baecc  test    byte ptr [rcx+1Ch], 1
0x1800baed0  jz      short loc_1800BAEF4
0x1800baed2  cmp     byte ptr [rcx+19h], 2
0x1800baed6  jb      short loc_1800BAEF4
0x1800baed8  mov     edx, 134h
0x1800baedd  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800baee4  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800baeeb  mov     rcx, [rcx+10h]
0x1800baeef  call    WPP_SF_s
0x1800baef4  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800baefb  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800baf00  call    _CxxThrowException_0
0x1800baf06  lea     rcx, [rsp+450h+var_418]
0x1800baf0b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800baf11  nop
0x1800baf12  lea     rcx, [rsp+450h+var_418]
0x1800baf17  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800baf1d  mov     rax, [rbx]
0x1800baf20  mov     r9d, 8
0x1800baf26  lea     r8, [rsp+450h+var_418]
0x1800baf2b  lea     rdx, aTimerid; "TimerId"
0x1800baf32  mov     rcx, rbx
0x1800baf35  mov     rax, [rax+368h]
0x1800baf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf41  cmp     eax, edi
0x1800baf43  jnz     short loc_1800BAFA6
0x1800baf45  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800baf4b  mov     edx, 0FFFFFFFEh
0x1800baf50  mov     rcx, rax
0x1800baf53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800baf59  lea     rax, WPP_GLOBAL_Control
0x1800baf60  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baf67  cmp     rcx, rax
0x1800baf6a  jz      short loc_1800BAF94
0x1800baf6c  test    byte ptr [rcx+1Ch], 1
0x1800baf70  jz      short loc_1800BAF94
0x1800baf72  cmp     byte ptr [rcx+19h], 2
0x1800baf76  jb      short loc_1800BAF94
0x1800baf78  mov     edx, 135h
0x1800baf7d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800baf84  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800baf8b  mov     rcx, [rcx+10h]
0x1800baf8f  call    WPP_SF_s
0x1800baf94  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800baf9b  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800bafa0  call    _CxxThrowException_0
0x1800bafa6  xor     edx, edx
0x1800bafa8  lea     r8d, [rdx+0Bh]
0x1800bafac  lea     rcx, [rbp+350h+var_3B8]
0x1800bafb0  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bafb6  nop
0x1800bafb7  mov     rax, [rbx]
0x1800bafba  mov     r9d, 0Bh
0x1800bafc0  lea     r8, [rbp+350h+var_3B8]
0x1800bafc4  lea     rdx, aSkipifpassed; "SkipIfPassed"
0x1800bafcb  mov     rcx, rbx
0x1800bafce  mov     rax, [rax+368h]
0x1800bafd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafda  cmp     eax, edi
0x1800bafdc  jnz     short loc_1800BB03F
0x1800bafde  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bafe4  mov     edx, 0FFFFFFFEh
0x1800bafe9  mov     rcx, rax
0x1800bafec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800baff2  lea     rax, WPP_GLOBAL_Control
0x1800baff9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb000  cmp     rcx, rax
0x1800bb003  jz      short loc_1800BB02D
0x1800bb005  test    byte ptr [rcx+1Ch], 1
0x1800bb009  jz      short loc_1800BB02D
0x1800bb00b  cmp     byte ptr [rcx+19h], 2
0x1800bb00f  jb      short loc_1800BB02D
0x1800bb011  mov     edx, 136h
0x1800bb016  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb01d  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb024  mov     rcx, [rcx+10h]
0x1800bb028  call    WPP_SF_s
0x1800bb02d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb034  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800bb039  call    _CxxThrowException_0
0x1800bb03f  or      edx, 0FFFFFFFFh
0x1800bb042  lea     r8d, [rdx+0Ch]
0x1800bb046  lea     rcx, [rsp+450h+var_3D8]
0x1800bb04b  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bb051  nop
0x1800bb052  mov     rax, [rbx]
0x1800bb055  lea     rcx, [rsp+450h+var_3D8]
0x1800bb05a  mov     [rsp+450h+var_430], rcx
0x1800bb05f  xor     r9d, r9d
0x1800bb062  lea     r8, aKey; "key"
0x1800bb069  lea     rdx, aTimerid; "TimerId"
0x1800bb070  mov     rcx, rbx
0x1800bb073  mov     rax, [rax+378h]
0x1800bb07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb07f  cmp     eax, edi
0x1800bb081  jnz     short loc_1800BB0E4
0x1800bb083  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb089  mov     edx, 0FFFFFFFEh
0x1800bb08e  mov     rcx, rax
0x1800bb091  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb097  lea     rax, WPP_GLOBAL_Control
0x1800bb09e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb0a5  cmp     rcx, rax
0x1800bb0a8  jz      short loc_1800BB0D2
0x1800bb0aa  test    byte ptr [rcx+1Ch], 1
0x1800bb0ae  jz      short loc_1800BB0D2
0x1800bb0b0  cmp     byte ptr [rcx+19h], 2
0x1800bb0b4  jb      short loc_1800BB0D2
0x1800bb0b6  mov     edx, 137h
0x1800bb0bb  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb0c2  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb0c9  mov     rcx, [rcx+10h]
0x1800bb0cd  call    WPP_SF_s
0x1800bb0d2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb0d9  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800bb0de  call    _CxxThrowException_0
0x1800bb0e4  or      edx, 0FFFFFFFFh
0x1800bb0e7  lea     r8d, [rdx+0Ch]
0x1800bb0eb  lea     rcx, [rsp+450h+var_3F8]
0x1800bb0f0  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bb0f6  nop
0x1800bb0f7  mov     rax, [rbx]
0x1800bb0fa  xor     r9d, r9d
0x1800bb0fd  lea     r8, [rsp+450h+var_3F8]
0x1800bb102  lea     rdx, aAbstract_1; "abstract"
0x1800bb109  mov     rcx, rbx
0x1800bb10c  mov     rax, [rax+3D8h]
0x1800bb113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb118  cmp     eax, edi
0x1800bb11a  jnz     short loc_1800BB17D
0x1800bb11c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb122  mov     edx, 0FFFFFFFEh
0x1800bb127  mov     rcx, rax
0x1800bb12a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb130  lea     rax, WPP_GLOBAL_Control
0x1800bb137  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb13e  cmp     rcx, rax
0x1800bb141  jz      short loc_1800BB16B
0x1800bb143  test    byte ptr [rcx+1Ch], 1
0x1800bb147  jz      short loc_1800BB16B
0x1800bb149  cmp     byte ptr [rcx+19h], 2
0x1800bb14d  jb      short loc_1800BB16B
0x1800bb14f  mov     edx, 138h
0x1800bb154  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb15b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb162  mov     rcx, [rcx+10h]
0x1800bb166  call    WPP_SF_s
0x1800bb16b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb172  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800bb177  call    _CxxThrowException_0
0x1800bb17d  lea     rcx, [rsp+450h+var_3F8]
0x1800bb182  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb188  nop
0x1800bb189  lea     rcx, [rsp+450h+var_3D8]
0x1800bb18e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb194  nop
0x1800bb195  lea     rcx, [rbp+350h+var_3B8]
0x1800bb199  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb19f  nop
0x1800bb1a0  lea     rcx, [rsp+450h+var_418]
0x1800bb1a5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb1ab  nop
0x1800bb1ac  lea     rcx, [rbp+350h+var_398]
0x1800bb1b0  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb1b6  nop
0x1800bb1b7  lea     rcx, [rbp+350h+var_370]; this
0x1800bb1bb  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800bb1c0  mov     rcx, [rbp+350h+var_10]
0x1800bb1c7  xor     rcx, rsp; StackCookie
0x1800bb1ca  call    __security_check_cookie
0x1800bb1cf  lea     r11, [rsp+450h+var_s0]
0x1800bb1d7  mov     rbx, [r11+18h]
0x1800bb1db  mov     rdi, [r11+20h]
0x1800bb1df  mov     rsp, r11
0x1800bb1e2  pop     rbp
0x1800bb1e3  retn
```
