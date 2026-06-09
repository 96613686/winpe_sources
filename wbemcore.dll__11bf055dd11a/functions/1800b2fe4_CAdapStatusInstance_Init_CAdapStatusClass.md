# CAdapStatusInstance::Init(CAdapStatusClass *)

- ea: `0x1800b2fe4`
- end: `0x1800b32eb`
- name: `?Init@CAdapStatusInstance@@QEAAXPEAVCAdapStatusClass@@@Z`
- size: `775`
- prototype: `void __fastcall(CAdapStatusInstance *__hidden this, struct CAdapStatusClass *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a6d08`

## callees

- `0x18000b140`
- `0x18000e8c0`
- `0x18008846c`
- `0x18008a658`
- `0x1800b2fe4`
- `0x1800ce510`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3128`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3128`
- `wbemcomn!?SetLong@CVar@@QEAAXJ@Z` at `0x1800b3236`
- `wbemcomn!?SetLong@CVar@@QEAAXJ@Z` at `0x1800b3236`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b3228`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b3228`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b32b8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b32c4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b32b8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b32c4`
- `wbemcomn!GetMemLogObject` at `0x1800b301c`
- `wbemcomn!GetMemLogObject` at `0x1800b30d8`
- `wbemcomn!GetMemLogObject` at `0x1800b3152`
- `wbemcomn!GetMemLogObject` at `0x1800b31c9`
- `wbemcomn!GetMemLogObject` at `0x1800b3259`
- `wbemcomn!GetMemLogObject` at `0x1800b301c`
- `wbemcomn!GetMemLogObject` at `0x1800b30d8`
- `wbemcomn!GetMemLogObject` at `0x1800b3152`
- `wbemcomn!GetMemLogObject` at `0x1800b31c9`
- `wbemcomn!GetMemLogObject` at `0x1800b3259`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b302a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b30e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3160`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b31d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3267`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b302a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b30e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3160`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b31d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3267`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b3141`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b31be`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b324e`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b3141`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b31be`
- `FastProx!?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b324e`
- `FastProx!?InitNew@CWbemInstance@@QEAAJPEAVCWbemClass@@HPEAVCDecorationPart@@@Z` at `0x1800b3012`
- `FastProx!?InitNew@CWbemInstance@@QEAAJPEAVCWbemClass@@HPEAVCDecorationPart@@@Z` at `0x1800b3012`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAdapStatusInstance::Init(CAdapStatusInstance *this, struct CAdapStatusClass *a2)
{
  CMemoryLog *MemLogObject; // rax
  int v4; // r15d
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  char pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v12[104]; // [rsp+A0h] [rbp-60h] BYREF

  if ( (int)CWbemInstance::InitNew(this, a2, 100, 0) < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v4 = StringCchPrintfW(v12, 0x64u, L"%04u%02u%02u%02u%02u%02u.%06u:000");
  if ( v4 < 0 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, v4);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v4);
    }
  }
  CVar::CVar((CVar *)v11, 8, v12);
  if ( CWbemInstance::SetPropValue(this, L"LastStartTime", (struct CVar *)v11, 0) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        161,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( CWbemInstance::SetPropValue(this, L"LastStopTime", (struct CVar *)v11, 0) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        162,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10);
  CVar::SetLong((CVar *)v10, 0);
  if ( CWbemInstance::SetPropValue(this, L"Status", (struct CVar *)v10, 0) == -2147217402 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        163,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v11);
}

```

## disassembly

```asm
0x1800b2fe4  mov     [rsp-8+arg_10], r12
0x1800b2fe9  push    rbp
0x1800b2fea  push    r14
0x1800b2fec  push    r15
0x1800b2fee  lea     rbp, [rsp-80h]
0x1800b2ff3  sub     rsp, 180h
0x1800b2ffa  mov     rax, cs:__security_cookie
0x1800b3001  xor     rax, rsp
0x1800b3004  mov     [rbp+90h+var_20], rax
0x1800b3008  mov     r12, rcx
0x1800b300b  xor     r9d, r9d
0x1800b300e  lea     r8d, [r9+64h]
0x1800b3012  call    cs:__imp_?InitNew@CWbemInstance@@QEAAJPEAVCWbemClass@@HPEAVCDecorationPart@@@Z; CWbemInstance::InitNew(CWbemClass *,int,CDecorationPart *)
0x1800b3018  test    eax, eax
0x1800b301a  jns     short loc_1800B307D
0x1800b301c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3022  mov     edx, 0FFFFFFFEh
0x1800b3027  mov     rcx, rax
0x1800b302a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3030  lea     r14, WPP_GLOBAL_Control
0x1800b3037  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b303e  cmp     rcx, r14
0x1800b3041  jz      short loc_1800B306B
0x1800b3043  test    byte ptr [rcx+1Ch], 1
0x1800b3047  jz      short loc_1800B306B
0x1800b3049  cmp     byte ptr [rcx+19h], 2
0x1800b304d  jb      short loc_1800B306B
0x1800b304f  mov     edx, 9Fh
0x1800b3054  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b305b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3062  mov     rcx, [rcx+10h]
0x1800b3066  call    WPP_SF_s
0x1800b306b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3072  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1800b3077  call    _CxxThrowException_0
0x1800b307d  mov     [rsp+190h+var_148], 0
0x1800b3086  mov     [rsp+190h+var_150], 0
0x1800b308f  mov     [rsp+190h+var_158], 0
0x1800b3098  mov     [rsp+190h+var_160], 0
0x1800b30a1  mov     [rsp+190h+var_168], 0
0x1800b30aa  mov     [rsp+190h+var_170], 0
0x1800b30b3  xor     r9d, r9d
0x1800b30b6  lea     r8, a04u02u02u02u02; "%04u%02u%02u%02u%02u%02u.%06u:000"
0x1800b30bd  lea     edx, [r9+64h]; unsigned __int64
0x1800b30c1  lea     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x1800b30c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b30ca  mov     r15d, eax
0x1800b30cd  lea     r14, WPP_GLOBAL_Control
0x1800b30d4  test    eax, eax
0x1800b30d6  jns     short loc_1800B311A
0x1800b30d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b30de  mov     edx, r15d
0x1800b30e1  mov     rcx, rax
0x1800b30e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b30ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b30f1  cmp     rcx, r14
0x1800b30f4  jz      short loc_1800B311A
0x1800b30f6  test    byte ptr [rcx+1Ch], 1
0x1800b30fa  jz      short loc_1800B311A
0x1800b30fc  cmp     byte ptr [rcx+19h], 2
0x1800b3100  jb      short loc_1800B311A
0x1800b3102  mov     edx, 0A0h
0x1800b3107  mov     r9d, r15d
0x1800b310a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3111  mov     rcx, [rcx+10h]
0x1800b3115  call    WPP_SF_d
0x1800b311a  lea     r8, [rbp+90h+var_F0]
0x1800b311e  mov     edx, 8
0x1800b3123  lea     rcx, [rsp+190h+var_118]
0x1800b3128  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b312e  nop
0x1800b312f  xor     r9d, r9d
0x1800b3132  lea     r8, [rsp+190h+var_118]
0x1800b3137  lea     rdx, aLaststarttime; "LastStartTime"
0x1800b313e  mov     rcx, r12
0x1800b3141  call    cs:__imp_?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z; CWbemInstance::SetPropValue(ushort const *,CVar *,long)
0x1800b3147  mov     r15d, 80041006h
0x1800b314d  cmp     eax, r15d
0x1800b3150  jnz     short loc_1800B31AC
0x1800b3152  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3158  mov     edx, 0FFFFFFFEh
0x1800b315d  mov     rcx, rax
0x1800b3160  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3166  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b316d  cmp     rcx, r14
0x1800b3170  jz      short loc_1800B319A
0x1800b3172  test    byte ptr [rcx+1Ch], 1
0x1800b3176  jz      short loc_1800B319A
0x1800b3178  cmp     byte ptr [rcx+19h], 2
0x1800b317c  jb      short loc_1800B319A
0x1800b317e  mov     edx, 0A1h
0x1800b3183  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b318a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3191  mov     rcx, [rcx+10h]
0x1800b3195  call    WPP_SF_s
0x1800b319a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b31a1  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1800b31a6  call    _CxxThrowException_0
0x1800b31ac  xor     r9d, r9d
0x1800b31af  lea     r8, [rsp+190h+var_118]
0x1800b31b4  lea     rdx, aLaststoptime; "LastStopTime"
0x1800b31bb  mov     rcx, r12
0x1800b31be  call    cs:__imp_?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z; CWbemInstance::SetPropValue(ushort const *,CVar *,long)
0x1800b31c4  cmp     eax, r15d
0x1800b31c7  jnz     short loc_1800B3223
0x1800b31c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b31cf  mov     edx, 0FFFFFFFEh
0x1800b31d4  mov     rcx, rax
0x1800b31d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b31dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b31e4  cmp     rcx, r14
0x1800b31e7  jz      short loc_1800B3211
0x1800b31e9  test    byte ptr [rcx+1Ch], 1
0x1800b31ed  jz      short loc_1800B3211
0x1800b31ef  cmp     byte ptr [rcx+19h], 2
0x1800b31f3  jb      short loc_1800B3211
0x1800b31f5  mov     edx, 0A2h
0x1800b31fa  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3201  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3208  mov     rcx, [rcx+10h]
0x1800b320c  call    WPP_SF_s
0x1800b3211  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3218  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1800b321d  call    _CxxThrowException_0
0x1800b3223  lea     rcx, [rsp+190h+var_138]
0x1800b3228  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b322e  nop
0x1800b322f  xor     edx, edx
0x1800b3231  lea     rcx, [rsp+190h+var_138]
0x1800b3236  call    cs:__imp_?SetLong@CVar@@QEAAXJ@Z; CVar::SetLong(long)
0x1800b323c  xor     r9d, r9d
0x1800b323f  lea     r8, [rsp+190h+var_138]
0x1800b3244  lea     rdx, aStatus; "Status"
0x1800b324b  mov     rcx, r12
0x1800b324e  call    cs:__imp_?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z; CWbemInstance::SetPropValue(ushort const *,CVar *,long)
0x1800b3254  cmp     eax, r15d
0x1800b3257  jnz     short loc_1800B32B3
0x1800b3259  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b325f  mov     edx, 0FFFFFFFEh
0x1800b3264  mov     rcx, rax
0x1800b3267  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b326d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3274  cmp     rcx, r14
0x1800b3277  jz      short loc_1800B32A1
0x1800b3279  test    byte ptr [rcx+1Ch], 1
0x1800b327d  jz      short loc_1800B32A1
0x1800b327f  cmp     byte ptr [rcx+19h], 2
0x1800b3283  jb      short loc_1800B32A1
0x1800b3285  mov     edx, 0A3h
0x1800b328a  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3291  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3298  mov     rcx, [rcx+10h]
0x1800b329c  call    WPP_SF_s
0x1800b32a1  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b32a8  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1800b32ad  call    _CxxThrowException_0
0x1800b32b3  lea     rcx, [rsp+190h+var_138]
0x1800b32b8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b32be  nop
0x1800b32bf  lea     rcx, [rsp+190h+var_118]
0x1800b32c4  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b32ca  mov     rcx, [rbp+90h+var_20]
0x1800b32ce  xor     rcx, rsp; StackCookie
0x1800b32d1  call    __security_check_cookie
0x1800b32d6  mov     r12, [rsp+190h+arg_10]
0x1800b32de  add     rsp, 180h
0x1800b32e5  pop     r15
0x1800b32e7  pop     r14
0x1800b32e9  pop     rbp
0x1800b32ea  retn
```
