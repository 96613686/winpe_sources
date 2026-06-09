# CQueueOverflowEventClass::Init(void)

- ea: `0x1800b8f30`
- end: `0x1800b922a`
- name: `?Init@CQueueOverflowEventClass@@QEAAXXZ`
- size: `762`
- prototype: `void __fastcall(CQueueOverflowEventClass *__hidden this)`
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
- `0x1800b5b90`
- `0x1800b8f30`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b8fff`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b913d`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b8fff`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b913d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b909d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b909d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b9091`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b9091`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91de`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91f6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91de`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b91f6`
- `wbemcomn!GetMemLogObject` at `0x1800b8f8d`
- `wbemcomn!GetMemLogObject` at `0x1800b902b`
- `wbemcomn!GetMemLogObject` at `0x1800b90cb`
- `wbemcomn!GetMemLogObject` at `0x1800b9178`
- `wbemcomn!GetMemLogObject` at `0x1800b8f8d`
- `wbemcomn!GetMemLogObject` at `0x1800b902b`
- `wbemcomn!GetMemLogObject` at `0x1800b90cb`
- `wbemcomn!GetMemLogObject` at `0x1800b9178`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8f9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b9039`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b90d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b9186`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8f9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b9039`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b90d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b9186`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b8f7e`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b8f7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CQueueOverflowEventClass::Init(CQueueOverflowEventClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v10[864]; // [rsp+A0h] [rbp-60h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v10);
  CEventDroppedEventClass::Init((CEventDroppedEventClass *)v10);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v10, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        232,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__EventQueueOverflowEvent");
  if ( (*(unsigned int (__fastcall **)(CQueueOverflowEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v9,
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
        233,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CQueueOverflowEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"CurrentQueueSize",
         v7,
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
        234,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, 8, L"bytes");
  if ( (*(unsigned int (__fastcall **)(CQueueOverflowEventClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"CurrentQueueSize",
         L"units",
         19,
         v8) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        235,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v9);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v10);
}

```

## disassembly

```asm
0x1800b8f30  mov     [rsp-8+arg_8], rbx
0x1800b8f35  mov     [rsp-8+arg_10], rdi
0x1800b8f3a  push    rbp
0x1800b8f3b  lea     rbp, [rsp-310h]
0x1800b8f43  sub     rsp, 410h
0x1800b8f4a  mov     rax, cs:__security_cookie
0x1800b8f51  xor     rax, rsp
0x1800b8f54  mov     [rbp+310h+var_10], rax
0x1800b8f5b  mov     rbx, rcx
0x1800b8f5e  lea     rcx, [rbp+310h+var_370]; this
0x1800b8f62  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b8f67  nop
0x1800b8f68  lea     rcx, [rbp+310h+var_370]; this
0x1800b8f6c  call    ?Init@CEventDroppedEventClass@@QEAAXXZ; CEventDroppedEventClass::Init(void)
0x1800b8f71  xor     r9d, r9d
0x1800b8f74  xor     r8d, r8d
0x1800b8f77  lea     rdx, [rbp+310h+var_370]
0x1800b8f7b  mov     rcx, rbx
0x1800b8f7e  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b8f84  mov     edi, 80041006h
0x1800b8f89  cmp     eax, edi
0x1800b8f8b  jnz     short loc_1800B8FEE
0x1800b8f8d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b8f93  mov     edx, 0FFFFFFFEh
0x1800b8f98  mov     rcx, rax
0x1800b8f9b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b8fa1  lea     rax, WPP_GLOBAL_Control
0x1800b8fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8faf  cmp     rcx, rax
0x1800b8fb2  jz      short loc_1800B8FDC
0x1800b8fb4  test    byte ptr [rcx+1Ch], 1
0x1800b8fb8  jz      short loc_1800B8FDC
0x1800b8fba  cmp     byte ptr [rcx+19h], 2
0x1800b8fbe  jb      short loc_1800B8FDC
0x1800b8fc0  mov     edx, 0E8h
0x1800b8fc5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8fcc  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8fd3  mov     rcx, [rcx+10h]
0x1800b8fd7  call    WPP_SF_s
0x1800b8fdc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8fe3  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b8fe8  call    _CxxThrowException_0
0x1800b8fee  lea     r8, aEventqueueover; "__EventQueueOverflowEvent"
0x1800b8ff5  mov     edx, 8
0x1800b8ffa  lea     rcx, [rsp+410h+var_398]
0x1800b8fff  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b9005  nop
0x1800b9006  mov     rax, [rbx]
0x1800b9009  xor     r9d, r9d
0x1800b900c  lea     r8, [rsp+410h+var_398]
0x1800b9011  lea     rdx, aClass_0; "__CLASS"
0x1800b9018  mov     rcx, rbx
0x1800b901b  mov     rax, [rax+368h]
0x1800b9022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9027  cmp     eax, edi
0x1800b9029  jnz     short loc_1800B908C
0x1800b902b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b9031  mov     edx, 0FFFFFFFEh
0x1800b9036  mov     rcx, rax
0x1800b9039  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b903f  lea     rax, WPP_GLOBAL_Control
0x1800b9046  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b904d  cmp     rcx, rax
0x1800b9050  jz      short loc_1800B907A
0x1800b9052  test    byte ptr [rcx+1Ch], 1
0x1800b9056  jz      short loc_1800B907A
0x1800b9058  cmp     byte ptr [rcx+19h], 2
0x1800b905c  jb      short loc_1800B907A
0x1800b905e  mov     edx, 0E9h
0x1800b9063  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b906a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b9071  mov     rcx, [rcx+10h]
0x1800b9075  call    WPP_SF_s
0x1800b907a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b9081  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b9086  call    _CxxThrowException_0
0x1800b908c  lea     rcx, [rsp+410h+var_3D8]
0x1800b9091  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b9097  nop
0x1800b9098  lea     rcx, [rsp+410h+var_3D8]
0x1800b909d  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b90a3  mov     rax, [rbx]
0x1800b90a6  mov     r9d, 13h
0x1800b90ac  lea     r8, [rsp+410h+var_3D8]
0x1800b90b1  lea     rdx, aCurrentqueuesi; "CurrentQueueSize"
0x1800b90b8  mov     rcx, rbx
0x1800b90bb  mov     rax, [rax+368h]
0x1800b90c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b90c7  cmp     eax, edi
0x1800b90c9  jnz     short loc_1800B912C
0x1800b90cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b90d1  mov     edx, 0FFFFFFFEh
0x1800b90d6  mov     rcx, rax
0x1800b90d9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b90df  lea     rax, WPP_GLOBAL_Control
0x1800b90e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b90ed  cmp     rcx, rax
0x1800b90f0  jz      short loc_1800B911A
0x1800b90f2  test    byte ptr [rcx+1Ch], 1
0x1800b90f6  jz      short loc_1800B911A
0x1800b90f8  cmp     byte ptr [rcx+19h], 2
0x1800b90fc  jb      short loc_1800B911A
0x1800b90fe  mov     edx, 0EAh
0x1800b9103  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b910a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b9111  mov     rcx, [rcx+10h]
0x1800b9115  call    WPP_SF_s
0x1800b911a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b9121  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b9126  call    _CxxThrowException_0
0x1800b912c  lea     r8, aBytes; "bytes"
0x1800b9133  mov     edx, 8
0x1800b9138  lea     rcx, [rsp+410h+var_3B8]
0x1800b913d  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b9143  nop
0x1800b9144  mov     rax, [rbx]
0x1800b9147  lea     rcx, [rsp+410h+var_3B8]
0x1800b914c  mov     [rsp+410h+var_3F0], rcx
0x1800b9151  mov     r9d, 13h
0x1800b9157  lea     r8, aUnits; "units"
0x1800b915e  lea     rdx, aCurrentqueuesi; "CurrentQueueSize"
0x1800b9165  mov     rcx, rbx
0x1800b9168  mov     rax, [rax+378h]
0x1800b916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9174  cmp     eax, edi
0x1800b9176  jnz     short loc_1800B91D9
0x1800b9178  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b917e  mov     edx, 0FFFFFFFEh
0x1800b9183  mov     rcx, rax
0x1800b9186  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b918c  lea     rax, WPP_GLOBAL_Control
0x1800b9193  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b919a  cmp     rcx, rax
0x1800b919d  jz      short loc_1800B91C7
0x1800b919f  test    byte ptr [rcx+1Ch], 1
0x1800b91a3  jz      short loc_1800B91C7
0x1800b91a5  cmp     byte ptr [rcx+19h], 2
0x1800b91a9  jb      short loc_1800B91C7
0x1800b91ab  mov     edx, 0EBh
0x1800b91b0  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b91b7  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b91be  mov     rcx, [rcx+10h]
0x1800b91c2  call    WPP_SF_s
0x1800b91c7  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b91ce  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b91d3  call    _CxxThrowException_0
0x1800b91d9  lea     rcx, [rsp+410h+var_3B8]
0x1800b91de  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b91e4  nop
0x1800b91e5  lea     rcx, [rsp+410h+var_3D8]
0x1800b91ea  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b91f0  nop
0x1800b91f1  lea     rcx, [rsp+410h+var_398]
0x1800b91f6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b91fc  nop
0x1800b91fd  lea     rcx, [rbp+310h+var_370]; this
0x1800b9201  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b9206  mov     rcx, [rbp+310h+var_10]
0x1800b920d  xor     rcx, rsp; StackCookie
0x1800b9210  call    __security_check_cookie
0x1800b9215  lea     r11, [rsp+410h+var_s0]
0x1800b921d  mov     rbx, [r11+18h]
0x1800b9221  mov     rdi, [r11+20h]
0x1800b9225  mov     rsp, r11
0x1800b9228  pop     rbp
0x1800b9229  retn
```
