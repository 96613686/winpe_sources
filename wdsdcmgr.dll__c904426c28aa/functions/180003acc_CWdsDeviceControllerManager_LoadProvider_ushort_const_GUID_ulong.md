# CWdsDeviceControllerManager::LoadProvider(ushort const *,_GUID *,ulong)

- ea: `0x180003acc`
- end: `0x1800040a6`
- name: `?LoadProvider@CWdsDeviceControllerManager@@AEAAKPEBGPEAU_GUID@@K@Z`
- size: `1498`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, const unsigned __int16 *, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800036dc`

## callees

- `0x180003acc`
- `0x180006ab0`
- `0x180006ff0`
- `0x180007798`
- `0x180013048`
- `0x1800130dc`
- `0x18001381c`
- `0x180013dcc`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x18001577c`
- `0x180015cc0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003fcc`
- `msvcrt!_wcsicmp` at `0x180003fcc`
- `KERNEL32!InitializeCriticalSection` at `0x180003e49`
- `KERNEL32!InitializeCriticalSection` at `0x180003e49`
- `WDSSRV!WdsPerfCounterAdd` at `0x180003bc5`
- `WDSSRV!WdsPerfCounterAdd` at `0x180003f64`
- `WDSSRV!WdsPerfCounterAdd` at `0x180003bc5`
- `WDSSRV!WdsPerfCounterAdd` at `0x180003f64`
- `ole32!CoCreateInstance` at `0x180003be4`
- `ole32!CoCreateInstance` at `0x180003be4`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d03`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d03`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::LoadProvider(
        CWdsDeviceControllerManager *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int a4)
{
  const unsigned __int16 *v4; // r14
  unsigned int v5; // esi
  LPVOID *v7; // r15
  unsigned __int64 v8; // r12
  int v9; // ebx
  const char *v10; // rdx
  __int64 v11; // rdi
  unsigned __int16 *v12; // rsi
  void *v13; // rcx
  int v15; // eax
  __int64 v16; // rcx
  const char *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  char *v21; // rax
  const char *v22; // rdx
  const char *v23; // rdx
  unsigned int v24; // eax
  const char *v25; // rdx
  unsigned __int16 *v26; // rax
  _QWORD *v27; // rax
  unsigned int v28; // edi
  unsigned int v29; // esi
  __int64 v30; // r14
  unsigned int v31; // ecx
  unsigned int v32; // eax
  int v33; // eax
  const char **v34; // r14
  __int64 v35; // r8
  __int64 v36; // r9
  const char *v37; // rdx
  __int64 v38; // [rsp+90h] [rbp-1h] BYREF
  __int64 v39; // [rsp+98h] [rbp+7h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+Fh] BYREF
  unsigned __int16 *v41; // [rsp+A8h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+1Fh] BYREF

  v4 = a2;
  v5 = a4;
  ppv = 0;
  v7 = 0;
  v39 = 0;
  v8 = 0;
  v38 = 0;
  v41 = 0;
  bstrString = 0;
  if ( g_ErrLibTraceFunctionEx )
  {
    v4 = a2;
    g_ErrLibTraceFunctionEx(
      0x20000u,
      L"Loading provider [%s] {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} at priority %u",
      a2,
      a3->Data1,
      a3->Data2,
      a3->Data3,
      a3->Data4[0],
      a3->Data4[1],
      a3->Data4[2],
      a3->Data4[3],
      a3->Data4[4],
      a3->Data4[5],
      a3->Data4[6],
      a3->Data4[7],
      a4);
    v5 = a4;
  }
  WdsPerfCounterAdd(44);
  v9 = CoCreateInstance(a3, 0, 1u, &IID_IWdsDeviceQueryController, &ppv);
  if ( (int)ElValidateHr(v9, v10, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x4FAu) < 0 )
    goto LABEL_5;
  v15 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IWdsDeviceManagementController, &v39);
  v16 = v39;
  if ( v15 < 0 )
    v16 = 0;
  v39 = v16;
  v9 = SysAllocStringHr(v4, &bstrString);
  if ( (int)ElValidateHr(v9, v17, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x50Eu) < 0
    || (v9 = CWdsMetadataFactory::CreateInstance(&v38, 0),
        (int)ElValidateHr(v9, v18, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x511u) < 0) )
  {
LABEL_5:
    if ( v9 < 0 && (v9 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v9;
    goto LABEL_7;
  }
  v11 = v38;
  v9 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64))(*(_QWORD *)ppv + 40LL))(ppv, bstrString, v38);
  if ( (int)ElValidateHr(v9, v19, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x514u) < 0
    || v39
    && (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 80LL))(v39, 0),
        (int)ElValidateHr(v9, v20, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x519u) < 0) )
  {
    if ( v9 < 0 && (v9 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v9;
    goto LABEL_8;
  }
  v21 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (LPVOID *)v21;
  if ( v21 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v21 + 24));
    *((_DWORD *)v7 + 16) = 0;
    v7[9] = 0;
    v7[10] = 0;
    v7[11] = 0;
    v7[12] = 0;
    v7[13] = 0;
    *((_DWORD *)v7 + 28) = 0;
    v7[15] = 0;
    v7[16] = 0;
    *((_DWORD *)v7 + 34) = 0;
    *v7 = 0;
    v7[1] = 0;
    *((_DWORD *)v7 + 4) = 0;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
  {
    v9 = 8;
    goto LABEL_8;
  }
  v9 = CMRSWLock::Initialize((CMRSWLock *)(v7 + 3), 0);
  if ( ElValidateWin32(v9, v22, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x524u) )
    goto LABEL_8;
  v9 = DuplicateStringW(v4, &v41);
  v24 = ElValidateWin32(v9, v23, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x527u);
  v25 = 0;
  if ( !v24 )
  {
    *v7 = ppv;
    v26 = v41;
    *((_DWORD *)v7 + 4) = v5;
    v12 = 0;
    v7[1] = v26;
    ppv = 0;
    if ( v39 )
    {
      v27 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = (unsigned __int64)v27;
      if ( v27 )
      {
        *v27 = 0;
        v27[1] = 0;
      }
      else
      {
        v8 = 0;
      }
      if ( !v8 )
      {
        v9 = 8;
        goto LABEL_9;
      }
      *(_QWORD *)v8 = v39;
      *(_QWORD *)(v8 + 8) = v7;
      v39 = 0;
      WdsPerfCounterAdd(46);
      v25 = 0;
    }
    v28 = 0;
    v29 = 1413;
    if ( *((_DWORD *)this + 43) )
    {
      while ( 1 )
      {
        v30 = 0;
        v31 = 0;
        if ( v28 < *((_DWORD *)this + 43) )
        {
          v25 = (const char *)v28;
          v30 = *(_QWORD *)(*((_QWORD *)this + 20) + 8LL * v28);
        }
        else
        {
          v31 = 1413;
        }
        v9 = v31;
        v32 = ElValidateWin32(v31, v25, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x54Bu);
        v25 = 0;
        if ( v32 )
          break;
        if ( a4 >= *(_DWORD *)(v30 + 16) )
        {
          if ( a4 != *(_DWORD *)(v30 + 16) || (v33 = _wcsicmp(a2, *(const wchar_t **)(v30 + 8)), v25 = 0, v33 >= 0) )
          {
            if ( ++v28 < *((_DWORD *)this + 43) )
              continue;
          }
        }
        goto LABEL_63;
      }
    }
    else
    {
LABEL_63:
      v34 = (const char **)((char *)this + 160);
      if ( v28 <= *((_DWORD *)this + 43) )
      {
        v29 = CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Grow((char *)this + 160);
        if ( !v29 )
        {
          LODWORD(v35) = *((_DWORD *)this + 43);
          if ( (unsigned int)v35 > v28 )
          {
            v36 = 8LL * (unsigned int)v35;
            do
            {
              v25 = *v34;
              v35 = (unsigned int)(v35 - 1);
              *(_QWORD *)&(*v34)[v36] = *(_QWORD *)&(*v34)[8 * v35];
              v36 -= 8;
            }
            while ( (unsigned int)v35 > v28 );
          }
          *(_QWORD *)&(*v34)[8 * v28] = v7;
          ++*((_DWORD *)this + 43);
        }
      }
      v9 = v29;
      if ( !ElValidateWin32(v29, v25, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x556u) )
      {
        v7 = 0;
        if ( v8 )
        {
          v9 = CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem((char *)this + 184, v8);
          v8 &= -(__int64)(ElValidateWin32(
                             v9,
                             v37,
                             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                             0x55Du) != 0);
        }
      }
    }
LABEL_7:
    v11 = v38;
LABEL_8:
    v12 = 0;
    goto LABEL_9;
  }
  v12 = v41;
LABEL_9:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, 0);
    ppv = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 16LL))(v39, 0);
    v39 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 16LL))(v11, 0);
  if ( v7 )
  {
    if ( *v7 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, 0);
      *v7 = 0;
    }
    v13 = v7[1];
    if ( v13 )
    {
      operator delete(v13);
      v7[1] = 0;
    }
    CMRSWLock::~CMRSWLock((CMRSWLock *)(v7 + 3));
    operator delete(v7);
  }
  if ( v8 )
  {
    if ( *(_QWORD *)v8 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v8 + 16LL))(*(_QWORD *)v8, 0);
      *(_QWORD *)v8 = 0;
    }
    *(_QWORD *)(v8 + 8) = 0;
    operator delete((void *)v8);
  }
  if ( v12 )
    operator delete(v12);
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003acc  mov     rax, rsp
0x180003acf  mov     [rax+8], rbx
0x180003ad3  mov     [rax+20h], r9d
0x180003ad7  mov     [rax+18h], r8
0x180003adb  mov     [rax+10h], rdx
0x180003adf  push    rbp
0x180003ae0  push    rsi
0x180003ae1  push    rdi
0x180003ae2  push    r12
0x180003ae4  push    r13
0x180003ae6  push    r14
0x180003ae8  push    r15
0x180003aea  lea     rbp, [rax-5Fh]
0x180003aee  sub     rsp, 0B0h
0x180003af5  mov     r14, rdx
0x180003af8  mov     esi, r9d
0x180003afb  xor     edx, edx
0x180003afd  mov     rax, r8
0x180003b00  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rdx; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003b07  mov     r13, rcx
0x180003b0a  mov     [rbp+57h+var_48], rdx
0x180003b0e  mov     r15d, edx
0x180003b11  mov     [rbp+57h+var_50], rdx
0x180003b15  mov     r12d, edx
0x180003b18  mov     [rbp+57h+var_58], rdx
0x180003b1c  mov     [rbp+57h+Block], rdx
0x180003b20  mov     [rbp+57h+var_40], rdx
0x180003b24  mov     [rbp+57h+bstrString], rdx
0x180003b28  jz      loc_180003BBB
0x180003b2e  movzx   r9d, byte ptr [rax+0Ch]
0x180003b33  movzx   r14d, word ptr [rax+4]
0x180003b38  movzx   r10d, byte ptr [rax+0Bh]
0x180003b3d  movzx   r11d, byte ptr [rax+0Ah]
0x180003b42  movzx   ebx, byte ptr [rax+9]
0x180003b46  movzx   edi, byte ptr [rax+8]
0x180003b4a  movzx   esi, word ptr [rax+6]
0x180003b4e  movzx   ecx, byte ptr [r8+0Fh]
0x180003b53  movzx   edx, byte ptr [r8+0Eh]
0x180003b58  movzx   r8d, byte ptr [r8+0Dh]
0x180003b5d  mov     eax, [rbp+57h+arg_18]
0x180003b60  mov     [rsp+70h], eax
0x180003b64  mov     rax, [rbp+57h+rclsid]
0x180003b68  mov     [rsp+0E0h+var_78], ecx
0x180003b6c  mov     ecx, 20000h
0x180003b71  mov     [rsp+0E0h+var_80], edx
0x180003b75  lea     rdx, aLoadingProvide; "Loading provider [%s] {%08X-%04X-%04X-%"...
0x180003b7c  mov     [rsp+0E0h+var_88], r8d
0x180003b81  mov     [rsp+0E0h+var_90], r9d
0x180003b86  mov     r9d, [rax]
0x180003b89  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003b90  mov     [rsp+0E0h+var_98], r10d
0x180003b95  mov     [rsp+0E0h+var_A0], r11d
0x180003b9a  mov     [rsp+0E0h+var_A8], ebx
0x180003b9e  mov     [rsp+0E0h+var_B0], edi
0x180003ba2  mov     [rsp+0E0h+var_B8], esi
0x180003ba6  mov     dword ptr [rsp+0E0h+ppv], r14d
0x180003bab  mov     r14, [rbp+57h+String1]
0x180003baf  mov     r8, r14
0x180003bb2  call    cs:__guard_dispatch_icall_fptr
0x180003bb8  mov     esi, [rbp+57h+arg_18]
0x180003bbb  mov     ebx, 1
0x180003bc0  mov     edx, ebx
0x180003bc2  lea     ecx, [rbx+2Bh]
0x180003bc5  call    cs:__imp_WdsPerfCounterAdd
0x180003bcb  mov     rcx, [rbp+57h+rclsid]; rclsid
0x180003bcf  lea     rax, [rbp+57h+var_48]
0x180003bd3  lea     r9, IID_IWdsDeviceQueryController; riid
0x180003bda  mov     [rsp+0E0h+ppv], rax; ppv
0x180003bdf  mov     r8d, ebx; dwClsContext
0x180003be2  xor     edx, edx; pUnkOuter
0x180003be4  call    cs:__imp_CoCreateInstance
0x180003bea  lea     rdi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003bf1  mov     r9d, 4FAh; unsigned int
0x180003bf7  mov     r8, rdi; char *
0x180003bfa  mov     ecx, eax; int
0x180003bfc  mov     ebx, eax
0x180003bfe  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180003c03  xor     edx, edx
0x180003c05  test    eax, eax
0x180003c07  jns     loc_180003D26
0x180003c0d  test    ebx, ebx
0x180003c0f  jns     short loc_180003C22
0x180003c11  mov     eax, ebx
0x180003c13  and     eax, 1FFF0000h
0x180003c18  cmp     eax, 70000h
0x180003c1d  jnz     short loc_180003C22
0x180003c1f  movzx   ebx, bx
0x180003c22  mov     rdi, [rbp+57h+var_58]
0x180003c26  mov     rsi, [rbp+57h+Block]
0x180003c2a  mov     rcx, [rbp+57h+var_48]
0x180003c2e  test    rcx, rcx
0x180003c31  jz      short loc_180003C46
0x180003c33  mov     rax, [rcx]
0x180003c36  mov     rax, [rax+10h]
0x180003c3a  call    cs:__guard_dispatch_icall_fptr
0x180003c40  xor     edx, edx
0x180003c42  mov     [rbp+57h+var_48], rdx
0x180003c46  mov     rcx, [rbp+57h+var_50]
0x180003c4a  test    rcx, rcx
0x180003c4d  jz      short loc_180003C62
0x180003c4f  mov     rax, [rcx]
0x180003c52  mov     rax, [rax+10h]
0x180003c56  call    cs:__guard_dispatch_icall_fptr
0x180003c5c  xor     edx, edx
0x180003c5e  mov     [rbp+57h+var_50], rdx
0x180003c62  test    rdi, rdi
0x180003c65  jz      short loc_180003C79
0x180003c67  mov     rax, [rdi]
0x180003c6a  mov     rcx, rdi
0x180003c6d  mov     rax, [rax+10h]
0x180003c71  call    cs:__guard_dispatch_icall_fptr
0x180003c77  xor     edx, edx
0x180003c79  test    r15, r15
0x180003c7c  jz      short loc_180003CBF
0x180003c7e  mov     rcx, [r15]
0x180003c81  test    rcx, rcx
0x180003c84  jz      short loc_180003C98
0x180003c86  mov     rax, [rcx]
0x180003c89  mov     rax, [rax+10h]
0x180003c8d  call    cs:__guard_dispatch_icall_fptr
0x180003c93  xor     edx, edx
0x180003c95  mov     [r15], rdx
0x180003c98  mov     rcx, [r15+8]; Block
0x180003c9c  test    rcx, rcx
0x180003c9f  jz      short loc_180003CAC
0x180003ca1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ca6  xor     edx, edx
0x180003ca8  mov     [r15+8], rdx
0x180003cac  lea     rcx, [r15+18h]; this
0x180003cb0  call    ??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x180003cb5  mov     rcx, r15; Block
0x180003cb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003cbd  xor     edx, edx
0x180003cbf  test    r12, r12
0x180003cc2  jz      short loc_180003CED
0x180003cc4  mov     rcx, [r12]
0x180003cc8  test    rcx, rcx
0x180003ccb  jz      short loc_180003CE0
0x180003ccd  mov     rax, [rcx]
0x180003cd0  mov     rax, [rax+10h]
0x180003cd4  call    cs:__guard_dispatch_icall_fptr
0x180003cda  xor     edx, edx
0x180003cdc  mov     [r12], rdx
0x180003ce0  mov     rcx, r12; Block
0x180003ce3  mov     [r12+8], rdx
0x180003ce8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ced  test    rsi, rsi
0x180003cf0  jz      short loc_180003CFA
0x180003cf2  mov     rcx, rsi; Block
0x180003cf5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003cfa  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180003cfe  test    rcx, rcx
0x180003d01  jz      short loc_180003D09
0x180003d03  call    cs:__imp_SysFreeString
0x180003d09  mov     eax, ebx
0x180003d0b  mov     rbx, [rsp+0E0h+arg_0]
0x180003d13  add     rsp, 0B0h
0x180003d1a  pop     r15
0x180003d1c  pop     r14
0x180003d1e  pop     r13
0x180003d20  pop     r12
0x180003d22  pop     rdi
0x180003d23  pop     rsi
0x180003d24  pop     rbp
0x180003d25  retn
0x180003d26  mov     rcx, [rbp+57h+var_48]
0x180003d2a  lea     r8, [rbp+57h+var_50]
0x180003d2e  lea     rdx, IID_IWdsDeviceManagementController
0x180003d35  mov     rax, [rcx]
0x180003d38  mov     rax, [rax]
0x180003d3b  call    cs:__guard_dispatch_icall_fptr
0x180003d41  mov     rcx, [rbp+57h+var_50]
0x180003d45  xor     edx, edx
0x180003d47  test    eax, eax
0x180003d49  cmovs   rcx, rdx
0x180003d4d  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180003d51  mov     [rbp+57h+var_50], rcx
0x180003d55  mov     rcx, r14; unsigned __int16 *
0x180003d58  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180003d5d  mov     r9d, 50Eh; unsigned int
0x180003d63  mov     r8, rdi; char *
0x180003d66  mov     ecx, eax; int
0x180003d68  mov     ebx, eax
0x180003d6a  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180003d6f  xor     edx, edx
0x180003d71  test    eax, eax
0x180003d73  js      loc_180003C0D
0x180003d79  lea     rcx, [rbp+57h+var_58]
0x180003d7d  call    ?CreateInstance@CWdsMetadataFactory@@SAJPEAPEAV?$CComObject@VCWdsMetadataFactory@@@ATL@@@Z; CWdsMetadataFactory::CreateInstance(ATL::CComObject<CWdsMetadataFactory> * *)
0x180003d82  mov     r9d, 511h; unsigned int
0x180003d88  mov     r8, rdi; char *
0x180003d8b  mov     ecx, eax; int
0x180003d8d  mov     ebx, eax
0x180003d8f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180003d94  xor     edx, edx
0x180003d96  test    eax, eax
0x180003d98  js      loc_180003C0D
0x180003d9e  mov     rcx, [rbp+57h+var_48]
0x180003da2  mov     rdi, [rbp+57h+var_58]
0x180003da6  mov     rdx, [rbp+57h+bstrString]
0x180003daa  mov     r8, rdi
0x180003dad  mov     rax, [rcx]
0x180003db0  mov     rax, [rax+28h]
0x180003db4  call    cs:__guard_dispatch_icall_fptr
0x180003dba  mov     r9d, 514h; unsigned int
0x180003dc0  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003dc7  mov     ecx, eax; int
0x180003dc9  mov     ebx, eax
0x180003dcb  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180003dd0  xor     edx, edx
0x180003dd2  test    eax, eax
0x180003dd4  jns     short loc_180003DF8
0x180003dd6  test    ebx, ebx
0x180003dd8  jns     loc_180003C26
0x180003dde  mov     eax, ebx
0x180003de0  and     eax, 1FFF0000h
0x180003de5  cmp     eax, 70000h
0x180003dea  jnz     loc_180003C26
0x180003df0  movzx   ebx, bx
0x180003df3  jmp     loc_180003C26
0x180003df8  mov     rcx, [rbp+57h+var_50]
0x180003dfc  test    rcx, rcx
0x180003dff  jz      short loc_180003E2A
0x180003e01  mov     rax, [rcx]
0x180003e04  mov     rax, [rax+50h]
0x180003e08  call    cs:__guard_dispatch_icall_fptr
0x180003e0e  mov     r9d, 519h; unsigned int
0x180003e14  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003e1b  mov     ecx, eax; int
0x180003e1d  mov     ebx, eax
0x180003e1f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180003e24  xor     edx, edx
0x180003e26  test    eax, eax
0x180003e28  js      short loc_180003DD6
0x180003e2a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e31  mov     ecx, 90h; unsigned __int64
0x180003e36  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003e3b  xor     edx, edx; unsigned int
0x180003e3d  mov     r15, rax
0x180003e40  test    rax, rax
0x180003e43  jz      short loc_180003E8E
0x180003e45  lea     rcx, [rax+18h]; lpCriticalSection
0x180003e49  call    cs:__imp_InitializeCriticalSection
0x180003e4f  xor     edx, edx
0x180003e51  mov     [r15+40h], edx
0x180003e55  xor     eax, eax
0x180003e57  mov     [r15+48h], rdx
0x180003e5b  mov     [r15+50h], rdx
0x180003e5f  mov     [r15+58h], rdx
0x180003e63  mov     [r15+60h], rax
0x180003e67  mov     [r15+68h], rax
0x180003e6b  mov     [r15+70h], edx
0x180003e6f  mov     [r15+78h], rdx
0x180003e73  mov     [r15+80h], rdx
0x180003e7a  mov     [r15+88h], edx
0x180003e81  mov     [r15], rdx
0x180003e84  mov     [r15+8], rdx
0x180003e88  mov     [r15+10h], edx
0x180003e8c  jmp     short loc_180003E91
0x180003e8e  mov     r15, rdx
0x180003e91  test    r15, r15
0x180003e94  jnz     short loc_180003E9F
0x180003e96  lea     ebx, [r15+8]
0x180003e9a  jmp     loc_180003C26
0x180003e9f  lea     rcx, [r15+18h]; this
0x180003ea3  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x180003ea8  mov     r9d, 524h; unsigned int
0x180003eae  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003eb5  mov     ecx, eax; unsigned int
0x180003eb7  mov     ebx, eax
0x180003eb9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003ebe  xor     edx, edx
0x180003ec0  test    eax, eax
0x180003ec2  jnz     loc_180003C26
0x180003ec8  lea     rdx, [rbp+57h+var_40]; unsigned __int16 **
0x180003ecc  mov     rcx, r14; unsigned __int16 *
0x180003ecf  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180003ed4  mov     r9d, 527h; unsigned int
0x180003eda  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003ee1  mov     ecx, eax; unsigned int
0x180003ee3  mov     ebx, eax
0x180003ee5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003eea  xor     edx, edx
0x180003eec  test    eax, eax
0x180003eee  jnz     loc_18000409D
0x180003ef4  mov     rax, [rbp+57h+var_48]
0x180003ef8  mov     [r15], rax
0x180003efb  mov     rax, [rbp+57h+var_40]
0x180003eff  mov     [r15+10h], esi
0x180003f03  mov     esi, edx
0x180003f05  mov     [r15+8], rax
0x180003f09  mov     [rbp+57h+var_48], rdx
0x180003f0d  mov     [rbp+57h+Block], rdx
0x180003f11  cmp     [rbp+57h+var_50], rdx
0x180003f15  jz      short loc_180003F6C
0x180003f17  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003f1e  lea     ecx, [rsi+10h]; unsigned __int64
0x180003f21  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003f26  xor     edx, edx
0x180003f28  mov     r12, rax
  ... truncated ...
```
