# CAbsoluteTimerInstructionClass::Init(void)

- ea: `0x1800b2624`
- end: `0x1800b2919`
- name: `?Init@CAbsoluteTimerInstructionClass@@QEAAXXZ`
- size: `757`
- prototype: `void __fastcall(CAbsoluteTimerInstructionClass *__hidden this)`
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
- `0x1800b2624`
- `0x1800badac`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b282c`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b282c`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b26f3`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b26f3`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b2791`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b2791`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b2785`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b2785`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28cd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28d9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28e5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28cd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28d9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b28e5`
- `wbemcomn!GetMemLogObject` at `0x1800b2681`
- `wbemcomn!GetMemLogObject` at `0x1800b271f`
- `wbemcomn!GetMemLogObject` at `0x1800b27bf`
- `wbemcomn!GetMemLogObject` at `0x1800b2867`
- `wbemcomn!GetMemLogObject` at `0x1800b2681`
- `wbemcomn!GetMemLogObject` at `0x1800b271f`
- `wbemcomn!GetMemLogObject` at `0x1800b27bf`
- `wbemcomn!GetMemLogObject` at `0x1800b2867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b268f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b272d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b27cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2875`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b268f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b272d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b27cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2875`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b2672`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b2672`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CAbsoluteTimerInstructionClass::Init(CAbsoluteTimerInstructionClass *this)
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
  CTimerInstructionClass::Init((CTimerInstructionClass *)v10);
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
        313,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__AbsoluteTimerInstruction");
  if ( (*(unsigned int (__fastcall **)(CAbsoluteTimerInstructionClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        314,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CAbsoluteTimerInstructionClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"EventDateTime",
         v7,
         101) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        315,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CAbsoluteTimerInstructionClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"EventDateTime",
         L"not_null",
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
        316,
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
0x1800b2624  mov     [rsp-8+arg_8], rbx
0x1800b2629  mov     [rsp-8+arg_10], rdi
0x1800b262e  push    rbp
0x1800b262f  lea     rbp, [rsp-310h]
0x1800b2637  sub     rsp, 410h
0x1800b263e  mov     rax, cs:__security_cookie
0x1800b2645  xor     rax, rsp
0x1800b2648  mov     [rbp+310h+var_10], rax
0x1800b264f  mov     rbx, rcx
0x1800b2652  lea     rcx, [rbp+310h+var_370]; this
0x1800b2656  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b265b  nop
0x1800b265c  lea     rcx, [rbp+310h+var_370]; this
0x1800b2660  call    ?Init@CTimerInstructionClass@@QEAAXXZ; CTimerInstructionClass::Init(void)
0x1800b2665  xor     r9d, r9d
0x1800b2668  xor     r8d, r8d
0x1800b266b  lea     rdx, [rbp+310h+var_370]
0x1800b266f  mov     rcx, rbx
0x1800b2672  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b2678  mov     edi, 80041006h
0x1800b267d  cmp     eax, edi
0x1800b267f  jnz     short loc_1800B26E2
0x1800b2681  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2687  mov     edx, 0FFFFFFFEh
0x1800b268c  mov     rcx, rax
0x1800b268f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2695  lea     rax, WPP_GLOBAL_Control
0x1800b269c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b26a3  cmp     rcx, rax
0x1800b26a6  jz      short loc_1800B26D0
0x1800b26a8  test    byte ptr [rcx+1Ch], 1
0x1800b26ac  jz      short loc_1800B26D0
0x1800b26ae  cmp     byte ptr [rcx+19h], 2
0x1800b26b2  jb      short loc_1800B26D0
0x1800b26b4  mov     edx, 139h
0x1800b26b9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b26c0  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b26c7  mov     rcx, [rcx+10h]
0x1800b26cb  call    WPP_SF_s
0x1800b26d0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b26d7  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b26dc  call    _CxxThrowException_0
0x1800b26e2  lea     r8, aAbsolutetimeri; "__AbsoluteTimerInstruction"
0x1800b26e9  mov     edx, 8
0x1800b26ee  lea     rcx, [rsp+410h+var_398]
0x1800b26f3  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b26f9  nop
0x1800b26fa  mov     rax, [rbx]
0x1800b26fd  xor     r9d, r9d
0x1800b2700  lea     r8, [rsp+410h+var_398]
0x1800b2705  lea     rdx, aClass_0; "__CLASS"
0x1800b270c  mov     rcx, rbx
0x1800b270f  mov     rax, [rax+368h]
0x1800b2716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b271b  cmp     eax, edi
0x1800b271d  jnz     short loc_1800B2780
0x1800b271f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2725  mov     edx, 0FFFFFFFEh
0x1800b272a  mov     rcx, rax
0x1800b272d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2733  lea     rax, WPP_GLOBAL_Control
0x1800b273a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2741  cmp     rcx, rax
0x1800b2744  jz      short loc_1800B276E
0x1800b2746  test    byte ptr [rcx+1Ch], 1
0x1800b274a  jz      short loc_1800B276E
0x1800b274c  cmp     byte ptr [rcx+19h], 2
0x1800b2750  jb      short loc_1800B276E
0x1800b2752  mov     edx, 13Ah
0x1800b2757  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b275e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b2765  mov     rcx, [rcx+10h]
0x1800b2769  call    WPP_SF_s
0x1800b276e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b2775  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b277a  call    _CxxThrowException_0
0x1800b2780  lea     rcx, [rsp+410h+var_3D8]
0x1800b2785  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b278b  nop
0x1800b278c  lea     rcx, [rsp+410h+var_3D8]
0x1800b2791  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b2797  mov     rax, [rbx]
0x1800b279a  mov     r9d, 65h ; 'e'
0x1800b27a0  lea     r8, [rsp+410h+var_3D8]
0x1800b27a5  lea     rdx, aEventdatetime; "EventDateTime"
0x1800b27ac  mov     rcx, rbx
0x1800b27af  mov     rax, [rax+368h]
0x1800b27b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b27bb  cmp     eax, edi
0x1800b27bd  jnz     short loc_1800B2820
0x1800b27bf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b27c5  mov     edx, 0FFFFFFFEh
0x1800b27ca  mov     rcx, rax
0x1800b27cd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b27d3  lea     rax, WPP_GLOBAL_Control
0x1800b27da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b27e1  cmp     rcx, rax
0x1800b27e4  jz      short loc_1800B280E
0x1800b27e6  test    byte ptr [rcx+1Ch], 1
0x1800b27ea  jz      short loc_1800B280E
0x1800b27ec  cmp     byte ptr [rcx+19h], 2
0x1800b27f0  jb      short loc_1800B280E
0x1800b27f2  mov     edx, 13Bh
0x1800b27f7  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b27fe  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b2805  mov     rcx, [rcx+10h]
0x1800b2809  call    WPP_SF_s
0x1800b280e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b2815  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b281a  call    _CxxThrowException_0
0x1800b2820  or      edx, 0FFFFFFFFh
0x1800b2823  lea     r8d, [rdx+0Ch]
0x1800b2827  lea     rcx, [rsp+410h+var_3B8]
0x1800b282c  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b2832  nop
0x1800b2833  mov     rax, [rbx]
0x1800b2836  lea     rcx, [rsp+410h+var_3B8]
0x1800b283b  mov     [rsp+410h+var_3F0], rcx
0x1800b2840  mov     r9d, 13h
0x1800b2846  lea     r8, aNotNull; "not_null"
0x1800b284d  lea     rdx, aEventdatetime; "EventDateTime"
0x1800b2854  mov     rcx, rbx
0x1800b2857  mov     rax, [rax+378h]
0x1800b285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2863  cmp     eax, edi
0x1800b2865  jnz     short loc_1800B28C8
0x1800b2867  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b286d  mov     edx, 0FFFFFFFEh
0x1800b2872  mov     rcx, rax
0x1800b2875  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b287b  lea     rax, WPP_GLOBAL_Control
0x1800b2882  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2889  cmp     rcx, rax
0x1800b288c  jz      short loc_1800B28B6
0x1800b288e  test    byte ptr [rcx+1Ch], 1
0x1800b2892  jz      short loc_1800B28B6
0x1800b2894  cmp     byte ptr [rcx+19h], 2
0x1800b2898  jb      short loc_1800B28B6
0x1800b289a  mov     edx, 13Ch
0x1800b289f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b28a6  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b28ad  mov     rcx, [rcx+10h]
0x1800b28b1  call    WPP_SF_s
0x1800b28b6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b28bd  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b28c2  call    _CxxThrowException_0
0x1800b28c8  lea     rcx, [rsp+410h+var_3B8]
0x1800b28cd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b28d3  nop
0x1800b28d4  lea     rcx, [rsp+410h+var_3D8]
0x1800b28d9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b28df  nop
0x1800b28e0  lea     rcx, [rsp+410h+var_398]
0x1800b28e5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b28eb  nop
0x1800b28ec  lea     rcx, [rbp+310h+var_370]; this
0x1800b28f0  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b28f5  mov     rcx, [rbp+310h+var_10]
0x1800b28fc  xor     rcx, rsp; StackCookie
0x1800b28ff  call    __security_check_cookie
0x1800b2904  lea     r11, [rsp+410h+var_s0]
0x1800b290c  mov     rbx, [r11+18h]
0x1800b2910  mov     rdi, [r11+20h]
0x1800b2914  mov     rsp, r11
0x1800b2917  pop     rbp
0x1800b2918  retn
```
