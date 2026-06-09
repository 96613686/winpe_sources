# CNotifyStatusClass::Init(void)

- ea: `0x180080054`
- end: `0x1800802e8`
- name: `?Init@CNotifyStatusClass@@QEAAXXZ`
- size: `660`
- prototype: `void __fastcall(CNotifyStatusClass *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x18007fab0`

## callees

- `0x180080054`
- `0x18008846c`
- `0x18008a658`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x180080226`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x180080226`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800800ee`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800800ee`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18008018b`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18008018b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180080180`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180080180`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802bb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802c6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802d1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802bb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802c6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800802d1`
- `wbemcomn!GetMemLogObject` at `0x18008007e`
- `wbemcomn!GetMemLogObject` at `0x18008011c`
- `wbemcomn!GetMemLogObject` at `0x1800801bb`
- `wbemcomn!GetMemLogObject` at `0x180080257`
- `wbemcomn!GetMemLogObject` at `0x18008007e`
- `wbemcomn!GetMemLogObject` at `0x18008011c`
- `wbemcomn!GetMemLogObject` at `0x1800801bb`
- `wbemcomn!GetMemLogObject` at `0x180080257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008008c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008012a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800801c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080265`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008008c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008012a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800801c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080265`
- `FastProx!?InitEmpty@CWbemClass@@QEAAJHH@Z` at `0x180080074`
- `FastProx!?InitEmpty@CWbemClass@@QEAAJHH@Z` at `0x180080074`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CNotifyStatusClass::Init(CNotifyStatusClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  _BYTE v6[32]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp+17h] BYREF
  _BYTE v8[32]; // [rsp+70h] [rbp+37h] BYREF
  char pExceptionObject; // [rsp+A8h] [rbp+6Fh] BYREF

  if ( (int)CWbemClass::InitEmpty(this, 1000, 1) < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, 8, L"__NotifyStatus");
  if ( (*(unsigned int (__fastcall **)(CNotifyStatusClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v8,
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
        25,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v6);
  CVar::SetAsNull((CVar *)v6);
  if ( (*(unsigned int (__fastcall **)(CNotifyStatusClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"StatusCode",
         v6,
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
        26,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CNotifyStatusClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"abstract",
         v7,
         19) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v6);
  CVar::~CVar((CVar *)v8);
}

```

## disassembly

```asm
0x180080054  mov     [rsp-8+arg_0], rbx
0x180080059  push    rbp
0x18008005a  lea     rbp, [rsp-57h]
0x18008005f  sub     rsp, 90h
0x180080066  mov     rbx, rcx
0x180080069  mov     edx, 3E8h
0x18008006e  mov     r8d, 1
0x180080074  call    cs:__imp_?InitEmpty@CWbemClass@@QEAAJHH@Z; CWbemClass::InitEmpty(int,int)
0x18008007a  test    eax, eax
0x18008007c  jns     short loc_1800800DE
0x18008007e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080084  mov     edx, 0FFFFFFFEh
0x180080089  mov     rcx, rax
0x18008008c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080092  lea     rax, WPP_GLOBAL_Control
0x180080099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800800a0  cmp     rcx, rax
0x1800800a3  jz      short loc_1800800CD
0x1800800a5  test    byte ptr [rcx+1Ch], 1
0x1800800a9  jz      short loc_1800800CD
0x1800800ab  cmp     byte ptr [rcx+19h], 2
0x1800800af  jb      short loc_1800800CD
0x1800800b1  mov     edx, 18h
0x1800800b6  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800800bd  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800800c4  mov     rcx, [rcx+10h]
0x1800800c8  call    WPP_SF_s
0x1800800cd  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800800d4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800800d8  call    _CxxThrowException_0
0x1800800de  lea     r8, aNotifystatus; "__NotifyStatus"
0x1800800e5  mov     edx, 8
0x1800800ea  lea     rcx, [rbp+57h+var_20]
0x1800800ee  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800800f4  nop
0x1800800f5  mov     rax, [rbx]
0x1800800f8  xor     r9d, r9d
0x1800800fb  lea     r8, [rbp+57h+var_20]
0x1800800ff  lea     rdx, aClass_0; "__CLASS"
0x180080106  mov     rcx, rbx
0x180080109  mov     rax, [rax+368h]
0x180080110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080115  cmp     eax, 80041006h
0x18008011a  jnz     short loc_18008017C
0x18008011c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080122  mov     edx, 0FFFFFFFEh
0x180080127  mov     rcx, rax
0x18008012a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080130  lea     rax, WPP_GLOBAL_Control
0x180080137  mov     rcx, cs:WPP_GLOBAL_Control
0x18008013e  cmp     rcx, rax
0x180080141  jz      short loc_18008016B
0x180080143  test    byte ptr [rcx+1Ch], 1
0x180080147  jz      short loc_18008016B
0x180080149  cmp     byte ptr [rcx+19h], 2
0x18008014d  jb      short loc_18008016B
0x18008014f  mov     edx, 19h
0x180080154  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18008015b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080162  mov     rcx, [rcx+10h]
0x180080166  call    WPP_SF_s
0x18008016b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080172  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080176  call    _CxxThrowException_0
0x18008017c  lea     rcx, [rbp+57h+var_60]
0x180080180  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180080186  nop
0x180080187  lea     rcx, [rbp+57h+var_60]
0x18008018b  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x180080191  mov     rax, [rbx]
0x180080194  mov     r9d, 13h
0x18008019a  lea     r8, [rbp+57h+var_60]
0x18008019e  lea     rdx, aStatuscode; "StatusCode"
0x1800801a5  mov     rcx, rbx
0x1800801a8  mov     rax, [rax+368h]
0x1800801af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801b4  cmp     eax, 80041006h
0x1800801b9  jnz     short loc_18008021B
0x1800801bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800801c1  mov     edx, 0FFFFFFFEh
0x1800801c6  mov     rcx, rax
0x1800801c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800801cf  lea     rax, WPP_GLOBAL_Control
0x1800801d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800801dd  cmp     rcx, rax
0x1800801e0  jz      short loc_18008020A
0x1800801e2  test    byte ptr [rcx+1Ch], 1
0x1800801e6  jz      short loc_18008020A
0x1800801e8  cmp     byte ptr [rcx+19h], 2
0x1800801ec  jb      short loc_18008020A
0x1800801ee  mov     edx, 1Ah
0x1800801f3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800801fa  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080201  mov     rcx, [rcx+10h]
0x180080205  call    WPP_SF_s
0x18008020a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080211  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080215  call    _CxxThrowException_0
0x18008021b  or      edx, 0FFFFFFFFh
0x18008021e  lea     r8d, [rdx+0Ch]
0x180080222  lea     rcx, [rbp+57h+var_40]
0x180080226  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x18008022c  nop
0x18008022d  mov     rax, [rbx]
0x180080230  mov     r9d, 13h
0x180080236  lea     r8, [rbp+57h+var_40]
0x18008023a  lea     rdx, aAbstract_1; "abstract"
0x180080241  mov     rcx, rbx
0x180080244  mov     rax, [rax+3D8h]
0x18008024b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080250  cmp     eax, 80041006h
0x180080255  jnz     short loc_1800802B7
0x180080257  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008025d  mov     edx, 0FFFFFFFEh
0x180080262  mov     rcx, rax
0x180080265  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008026b  lea     rax, WPP_GLOBAL_Control
0x180080272  mov     rcx, cs:WPP_GLOBAL_Control
0x180080279  cmp     rcx, rax
0x18008027c  jz      short loc_1800802A6
0x18008027e  test    byte ptr [rcx+1Ch], 1
0x180080282  jz      short loc_1800802A6
0x180080284  cmp     byte ptr [rcx+19h], 2
0x180080288  jb      short loc_1800802A6
0x18008028a  mov     edx, 1Bh
0x18008028f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080296  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18008029d  mov     rcx, [rcx+10h]
0x1800802a1  call    WPP_SF_s
0x1800802a6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800802ad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800802b1  call    _CxxThrowException_0
0x1800802b7  lea     rcx, [rbp+57h+var_40]
0x1800802bb  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800802c1  nop
0x1800802c2  lea     rcx, [rbp+57h+var_60]
0x1800802c6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800802cc  nop
0x1800802cd  lea     rcx, [rbp+57h+var_20]
0x1800802d1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800802d7  mov     rbx, [rsp+90h+arg_0]
0x1800802df  add     rsp, 90h
0x1800802e6  pop     rbp
0x1800802e7  retn
```
