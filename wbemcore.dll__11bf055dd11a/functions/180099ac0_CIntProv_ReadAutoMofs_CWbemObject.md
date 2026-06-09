# CIntProv::ReadAutoMofs(CWbemObject *)

- ea: `0x180099ac0`
- end: `0x180099d28`
- name: `?ReadAutoMofs@CIntProv@@QEAAJPEAVCWbemObject@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(CIntProv *__hidden this, struct CWbemObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098ab4`

## callees

- `0x18000b140`
- `0x180099ac0`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180099c39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180099c39`
- `wbemcomn!?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ` at `0x180099ca0`
- `wbemcomn!?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ` at `0x180099ca0`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180099b08`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180099b08`
- `wbemcomn!??0CSafeArray@@QEAA@HHHH@Z` at `0x180099b48`
- `wbemcomn!??0CSafeArray@@QEAA@HHHH@Z` at `0x180099b48`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x180099bf3`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x180099cd9`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x180099bf3`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x180099cd9`
- `wbemcomn!?SetBSTRAt@CSafeArray@@QEAAHHPEAG@Z` at `0x180099c27`
- `wbemcomn!?SetBSTRAt@CSafeArray@@QEAAHHPEAG@Z` at `0x180099c27`
- `wbemcomn!?Trim@CSafeArray@@QEAAHXZ` at `0x180099c79`
- `wbemcomn!?Trim@CSafeArray@@QEAAHXZ` at `0x180099c79`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180099ae8`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180099ae8`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099b1b`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099c09`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099cef`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099d0a`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099b1b`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099c09`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099cef`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180099d0a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099bfd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099ce3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099cfe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099bfd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099ce3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099cfe`
- `wbemcomn!GetMemLogObject` at `0x180099b9d`
- `wbemcomn!GetMemLogObject` at `0x180099b9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099bab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099bab`
- `OLEAUT32!__imp_SysAllocString` at `0x180099b8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180099b8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180099c30`
- `OLEAUT32!__imp_SysFreeString` at `0x180099c30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CIntProv::ReadAutoMofs(CIntProv *this, struct CWbemObject *a2)
{
  unsigned __int16 *MultiStr; // rax
  unsigned __int16 *v4; // rbx
  unsigned int v6; // r15d
  unsigned int v7; // esi
  const OLECHAR *v8; // rdi
  int v9; // r12d
  unsigned __int16 *v10; // rax
  OLECHAR *v11; // r14
  CMemoryLog *MemLogObject; // rax
  __int64 v13; // rax
  unsigned int v14; // edi
  unsigned int v15; // [rsp+30h] [rbp-B8h] BYREF
  int i; // [rsp+34h] [rbp-B4h]
  unsigned int v17; // [rsp+38h] [rbp-B0h]
  const OLECHAR *v18; // [rsp+40h] [rbp-A8h]
  unsigned __int16 *v19; // [rsp+48h] [rbp-A0h]
  _BYTE v20[24]; // [rsp+50h] [rbp-98h] BYREF
  __int128 v21; // [rsp+68h] [rbp-80h] BYREF
  __int64 v22; // [rsp+78h] [rbp-70h]
  _BYTE v23[104]; // [rsp+80h] [rbp-68h] BYREF

  Registry::Registry((Registry *)v20, L"Software\\Microsoft\\WBEM\\CIMOM", 1u);
  v15 = 0;
  MultiStr = Registry::GetMultiStr((Registry *)v20, L"Autorecover MOFs", &v15);
  v4 = MultiStr;
  if ( MultiStr )
  {
    v19 = MultiStr;
    CSafeArray::CSafeArray((CSafeArray *)v23, 8, 2, 32, 32);
    v6 = v15 >> 1;
    v7 = 0;
    v17 = 0;
    v8 = v4;
    v18 = v4;
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      while ( 1 )
      {
        if ( v7 >= v6 )
        {
          CSafeArray::Trim((CSafeArray *)v23);
          v21 = 0;
          v22 = 0;
          LOWORD(v21) = 8200;
          *((_QWORD *)&v21 + 1) = CSafeArray::GetArray((CSafeArray *)v23);
          v14 = (*(__int64 (__fastcall **)(struct CWbemObject *, const wchar_t *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)a2 + 40LL))(
                  a2,
                  L"AutorecoverMofs",
                  0,
                  &v21,
                  0);
          CSafeArray::~CSafeArray((CSafeArray *)v23);
          CWin32DefaultArena::WbemMemFree(v4);
          Registry::~Registry((Registry *)v20);
          return v14;
        }
        if ( *v8 )
          break;
        v18 = ++v8;
        v17 = ++v7;
      }
      v10 = SysAllocString(v8);
      v11 = v10;
      if ( !v10 )
        break;
      CSafeArray::SetBSTRAt((CSafeArray *)v23, v9, v10);
      SysFreeString(v11);
      v13 = (unsigned int)(lstrlenW(v8) + 1);
      v7 += v13;
      v17 = v7;
      v8 += v13;
      v18 = v8;
      ++v9;
    }
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_74d77713876d364524dd83337d5790f1_Traceguids, 2147749894LL);
    }
    CSafeArray::~CSafeArray((CSafeArray *)v23);
    CWin32DefaultArena::WbemMemFree(v4);
    Registry::~Registry((Registry *)v20);
    return 2147749894LL;
  }
  else
  {
    Registry::~Registry((Registry *)v20);
    return 0;
  }
}

```

## disassembly

```asm
0x180099ac0  push    rbx
0x180099ac2  push    rsi
0x180099ac3  push    rdi
0x180099ac4  push    r12
0x180099ac6  push    r13
0x180099ac8  push    r14
0x180099aca  push    r15
0x180099acc  sub     rsp, 0B0h
0x180099ad3  mov     r13, rdx
0x180099ad6  mov     r8d, 1
0x180099adc  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x180099ae3  lea     rcx, [rsp+0E8h+var_98]
0x180099ae8  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180099aee  nop
0x180099aef  xor     r14d, r14d
0x180099af2  mov     [rsp+0E8h+var_B8], r14d
0x180099af7  lea     r8, [rsp+0E8h+var_B8]
0x180099afc  lea     rdx, aAutorecoverMof_0; "Autorecover MOFs"
0x180099b03  lea     rcx, [rsp+0E8h+var_98]
0x180099b08  call    cs:__imp_?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z; Registry::GetMultiStr(ushort const *,ulong &)
0x180099b0e  mov     rbx, rax
0x180099b11  test    rax, rax
0x180099b14  jnz     short loc_180099B28
0x180099b16  lea     rcx, [rsp+0E8h+var_98]
0x180099b1b  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180099b21  xor     eax, eax
0x180099b23  jmp     loc_180099D15
0x180099b28  mov     [rsp+0E8h+var_A0], rbx
0x180099b2d  mov     r9d, 20h ; ' '
0x180099b33  mov     [rsp+0E8h+var_C8], r9d
0x180099b38  lea     edx, [r9-18h]
0x180099b3c  lea     r8d, [r9-1Eh]
0x180099b40  lea     rcx, [rsp+0E8h+var_68]
0x180099b48  call    cs:__imp_??0CSafeArray@@QEAA@HHHH@Z; CSafeArray::CSafeArray(int,int,int,int)
0x180099b4e  nop
0x180099b4f  mov     [rsp+0E8h+var_A8], r14
0x180099b54  mov     [rsp+0E8h+var_B4], r14d
0x180099b59  mov     r15d, [rsp+0E8h+var_B8]
0x180099b5e  shr     r15d, 1
0x180099b61  mov     esi, r14d
0x180099b64  mov     [rsp+0E8h+var_B0], r14d
0x180099b69  mov     rdi, rbx
0x180099b6c  mov     [rsp+0E8h+var_A8], rbx
0x180099b71  mov     r12d, r14d
0x180099b74  mov     [rsp+0E8h+var_B4], r14d
0x180099b79  cmp     esi, r15d
0x180099b7c  jnb     loc_180099C71
0x180099b82  cmp     [rdi], r14w
0x180099b86  jz      loc_180099C5D
0x180099b8c  mov     rcx, rdi; psz
0x180099b8f  call    cs:__imp_SysAllocString
0x180099b95  mov     r14, rax
0x180099b98  test    rax, rax
0x180099b9b  jnz     short loc_180099C19
0x180099b9d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180099ba3  mov     edx, 80041006h
0x180099ba8  mov     rcx, rax
0x180099bab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180099bb1  lea     rax, WPP_GLOBAL_Control
0x180099bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bbf  cmp     rcx, rax
0x180099bc2  jz      short loc_180099BEB
0x180099bc4  test    byte ptr [rcx+1Ch], 1
0x180099bc8  jz      short loc_180099BEB
0x180099bca  cmp     byte ptr [rcx+19h], 2
0x180099bce  jb      short loc_180099BEB
0x180099bd0  lea     edx, [r14+1Ch]
0x180099bd4  mov     r9d, 80041006h
0x180099bda  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x180099be1  mov     rcx, [rcx+10h]
0x180099be5  call    WPP_SF_d
0x180099bea  nop
0x180099beb  lea     rcx, [rsp+0E8h+var_68]
0x180099bf3  call    cs:__imp_??1CSafeArray@@QEAA@XZ; CSafeArray::~CSafeArray(void)
0x180099bf9  nop
0x180099bfa  mov     rcx, rbx
0x180099bfd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180099c03  nop
0x180099c04  lea     rcx, [rsp+0E8h+var_98]
0x180099c09  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180099c0f  mov     eax, 80041006h
0x180099c14  jmp     loc_180099D15
0x180099c19  mov     r8, r14
0x180099c1c  mov     edx, r12d
0x180099c1f  lea     rcx, [rsp+0E8h+var_68]
0x180099c27  call    cs:__imp_?SetBSTRAt@CSafeArray@@QEAAHHPEAG@Z; CSafeArray::SetBSTRAt(int,ushort *)
0x180099c2d  mov     rcx, r14; bstrString
0x180099c30  call    cs:__imp_SysFreeString
0x180099c36  mov     rcx, rdi; lpString
0x180099c39  call    cs:__imp_lstrlenW
0x180099c3f  inc     eax
0x180099c41  add     esi, eax
0x180099c43  mov     [rsp+0E8h+var_B0], esi
0x180099c47  lea     rdi, [rdi+rax*2]
0x180099c4b  mov     [rsp+0E8h+var_A8], rdi
0x180099c50  inc     r12d
0x180099c53  mov     [rsp+0E8h+var_B4], r12d
0x180099c58  xor     r14d, r14d
0x180099c5b  jmp     short loc_180099C6C
0x180099c5d  add     rdi, 2
0x180099c61  mov     [rsp+0E8h+var_A8], rdi
0x180099c66  inc     esi
0x180099c68  mov     [rsp+0E8h+var_B0], esi
0x180099c6c  jmp     loc_180099B79
0x180099c71  lea     rcx, [rsp+0E8h+var_68]
0x180099c79  call    cs:__imp_?Trim@CSafeArray@@QEAAHXZ; CSafeArray::Trim(void)
0x180099c7f  xorps   xmm0, xmm0
0x180099c82  xor     eax, eax
0x180099c84  movups  [rsp+0E8h+var_80], xmm0
0x180099c89  mov     [rsp+0E8h+var_70], rax
0x180099c8e  mov     eax, 2008h
0x180099c93  mov     word ptr [rsp+0E8h+var_80], ax
0x180099c98  lea     rcx, [rsp+0E8h+var_68]
0x180099ca0  call    cs:__imp_?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ; CSafeArray::GetArray(void)
0x180099ca6  mov     qword ptr [rsp+0E8h+var_80+8], rax
0x180099cab  mov     rax, [r13+0]
0x180099caf  mov     [rsp+0E8h+var_C8], r14d
0x180099cb4  lea     r9, [rsp+0E8h+var_80]
0x180099cb9  xor     r8d, r8d
0x180099cbc  lea     rdx, aAutorecovermof; "AutorecoverMofs"
0x180099cc3  mov     rcx, r13
0x180099cc6  mov     rax, [rax+28h]
0x180099cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ccf  mov     edi, eax
0x180099cd1  lea     rcx, [rsp+0E8h+var_68]
0x180099cd9  call    cs:__imp_??1CSafeArray@@QEAA@XZ; CSafeArray::~CSafeArray(void)
0x180099cdf  nop
0x180099ce0  mov     rcx, rbx
0x180099ce3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180099ce9  nop
0x180099cea  lea     rcx, [rsp+0E8h+var_98]
0x180099cef  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180099cf5  mov     eax, edi
0x180099cf7  jmp     short loc_180099D15
0x180099cf9  mov     rcx, [rsp+0E8h+var_A0]
0x180099cfe  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180099d04  nop
0x180099d05  lea     rcx, [rsp+0E8h+var_98]
0x180099d0a  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180099d10  mov     eax, 80041006h
0x180099d15  add     rsp, 0B0h
0x180099d1c  pop     r15
0x180099d1e  pop     r14
0x180099d20  pop     r13
0x180099d22  pop     r12
0x180099d24  pop     rdi
0x180099d25  pop     rsi
0x180099d26  pop     rbx
0x180099d27  retn
```
