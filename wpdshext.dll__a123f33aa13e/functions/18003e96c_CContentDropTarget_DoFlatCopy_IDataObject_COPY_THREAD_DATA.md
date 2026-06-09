# CContentDropTarget::_DoFlatCopy(IDataObject *,COPY_THREAD_DATA *)

- ea: `0x18003e96c`
- end: `0x18003ee94`
- name: `?_DoFlatCopy@CContentDropTarget@@AEAAJPEAUIDataObject@@PEAVCOPY_THREAD_DATA@@@Z`
- size: `1320`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IDataObject *, struct COPY_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f360`

## callees

- `0x18000c180`
- `0x180017c88`
- `0x1800194d8`
- `0x1800285c8`
- `0x180028ea8`
- `0x18002ff5c`
- `0x180035590`
- `0x18003e96c`
- `0x180054524`
- `0x1800545c8`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003eba7`
- `KERNEL32!Sleep` at `0x18003ed39`
- `KERNEL32!Sleep` at `0x18003eba7`
- `KERNEL32!Sleep` at `0x18003ed39`
- `KERNEL32!GetCurrentThreadId` at `0x18003eb01`
- `KERNEL32!GetCurrentThreadId` at `0x18003eb4c`
- `KERNEL32!GetCurrentThreadId` at `0x18003eb01`
- `KERNEL32!GetCurrentThreadId` at `0x18003eb4c`
- `ole32!CoTaskMemFree` at `0x18003ee0e`
- `ole32!CoTaskMemFree` at `0x18003ee1e`
- `ole32!CoTaskMemFree` at `0x18003ee0e`
- `ole32!CoTaskMemFree` at `0x18003ee1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDropTarget::_DoFlatCopy(CContentDropTarget *this, struct IDataObject *a2, CProgressUI **a3)
{
  int v6; // eax
  int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // ebx
  DWORD v12; // eax
  int v13; // r14d
  int v14; // esi
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // r14d
  int v20; // esi
  unsigned int v21; // esi
  unsigned int v22; // r14d
  LPVOID *v23; // rsi
  unsigned int i; // edi
  unsigned int v26; // [rsp+50h] [rbp-B0h] BYREF
  struct IPortableDevice *v27; // [rsp+58h] [rbp-A8h] BYREF
  struct IPortableDeviceContent *v28; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v30[264]; // [rsp+70h] [rbp-90h] BYREF

  pv = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64))(**((_QWORD **)this + 10) + 144LL))(
         *((_QWORD *)this + 10),
         *(_QWORD *)(*((_QWORD *)this + 10) + 64LL),
         (char *)a3 + 3408,
         260);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_37;
    v9 = 29;
LABEL_36:
    WPP_SF_d(v8[2], v9, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v6);
LABEL_37:
    CContentDropTarget::_DisplayErrorMessage(this, v7, 0, (struct COPY_THREAD_DATA *)a3, 0);
    goto LABEL_59;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 10) + 96LL))(
          *((_QWORD *)this + 10),
          v30,
          260);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(CProgressUI *, CProgressUI **, struct IDataObject *, __int64, int, _DWORD, LPVOID *, unsigned int *))(*(_QWORD *)a3[559] + 64LL))(
           a3[559],
           a3,
           a2,
           2,
           (*(_DWORD *)a3 & 2) != 0 ? 112 : 110,
           0,
           &pv,
           &v26);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_37;
      v9 = 31;
      goto LABEL_36;
    }
    if ( a3[557] )
    {
      v13 = 0;
      v14 = 0;
      while ( !*((_DWORD *)a3[557] + 26) )
      {
        IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
        CurrentThreadId = GetCurrentThreadId();
        v7 = CDeviceCache::s_BindToPortableDevice(v30, CurrentThreadId, 0, 0, IsDelegateFolder, &v27);
        if ( v7 != -2147024726 )
          goto LABEL_23;
        if ( !v13 )
        {
          v13 = 1;
          v14 = 1;
          CProgressUI::_StartMarquee(a3[557]);
        }
        if ( *((_DWORD *)a3[557] + 26) )
          break;
        Sleep(0x5DCu);
      }
      v7 = -2147023673;
LABEL_23:
      if ( v14 )
        CProgressUI::_StopMarquee(a3[557]);
      if ( *((_DWORD *)a3[557] + 26) )
      {
        v7 = -2147023673;
        goto LABEL_28;
      }
    }
    else
    {
      v11 = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
      v12 = GetCurrentThreadId();
      v7 = CDeviceCache::s_BindToPortableDevice(v30, v12, 0, 0, v11, &v27);
    }
    if ( v7 < 0 )
    {
LABEL_28:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_59;
      v18 = 32;
      goto LABEL_31;
    }
    v6 = (*(__int64 (__fastcall **)(CProgressUI *, CProgressUI **, struct IPortableDevice *))(*(_QWORD *)a3[559] + 72LL))(
           a3[559],
           a3,
           v27);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_37;
      v9 = 33;
      goto LABEL_36;
    }
    if ( a3[557] )
    {
      v19 = 0;
      v20 = 0;
      while ( !*((_DWORD *)a3[557] + 26) )
      {
        v7 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v27->lpVtbl->Content)(
               v27,
               &v28);
        if ( v7 != -2147024726 )
          goto LABEL_52;
        if ( !v19 )
        {
          v19 = 1;
          v20 = 1;
          CProgressUI::_StartMarquee(a3[557]);
        }
        if ( *((_DWORD *)a3[557] + 26) )
          break;
        Sleep(0x5DCu);
      }
      v7 = -2147023673;
LABEL_52:
      if ( v20 )
        CProgressUI::_StopMarquee(a3[557]);
      if ( *((_DWORD *)a3[557] + 26) )
      {
        v7 = -2147023673;
LABEL_41:
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_59;
        v18 = 34;
LABEL_31:
        WPP_SF_d(v17[2], v18, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v7);
        goto LABEL_59;
      }
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v27->lpVtbl->Content)(
             v27,
             &v28);
    }
    if ( v7 >= 0 )
    {
      v21 = 0;
      do
      {
        if ( v21 >= v26 )
          break;
        v7 = CContentDropTarget::_DoInsert(
               this,
               *((const struct _ITEMIDLIST **)pv + v21++),
               *(struct _ITEMIDLIST **)(*((_QWORD *)this + 10) + 64LL),
               v27,
               v28,
               0,
               0,
               0,
               (struct COPY_THREAD_DATA *)a3);
      }
      while ( v7 >= 0 );
      goto LABEL_59;
    }
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)v10);
LABEL_59:
  ChangeNotify(4096, 0, *(LPCVOID *)(*((_QWORD *)this + 10) + 64LL), 0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 160LL))(
    *((_QWORD *)this + 10),
    *(_QWORD *)(*((_QWORD *)this + 10) + 64LL));
  v22 = v26;
  v23 = (LPVOID *)pv;
  for ( i = 0; i < v22; ++i )
    CoTaskMemFree(v23[i]);
  CoTaskMemFree(v23);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e96c  mov     [rsp-8+arg_18], rbx
0x18003e971  push    rbp
0x18003e972  push    rsi
0x18003e973  push    rdi
0x18003e974  push    r12
0x18003e976  push    r13
0x18003e978  push    r14
0x18003e97a  push    r15
0x18003e97c  lea     rbp, [rsp-190h]
0x18003e984  sub     rsp, 290h
0x18003e98b  mov     rax, cs:__security_cookie
0x18003e992  xor     rax, rsp
0x18003e995  mov     [rbp+1C0h+var_40], rax
0x18003e99c  mov     rdi, r8
0x18003e99f  mov     rsi, rdx
0x18003e9a2  mov     r15, rcx
0x18003e9a5  xor     r12d, r12d
0x18003e9a8  mov     [rsp+2C0h+pv], r12
0x18003e9ad  mov     [rsp+2C0h+var_270], r12d
0x18003e9b2  mov     [rsp+2C0h+var_268], r12
0x18003e9b7  mov     [rsp+2C0h+var_260], r12
0x18003e9bc  mov     rcx, [rcx+50h]
0x18003e9c0  mov     rax, [rcx]
0x18003e9c3  add     r8, 0D50h
0x18003e9ca  mov     r9d, 104h
0x18003e9d0  mov     rdx, [rcx+40h]
0x18003e9d4  mov     rax, [rax+90h]
0x18003e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9e0  mov     ebx, eax
0x18003e9e2  lea     r14, WPP_GLOBAL_Control
0x18003e9e9  lea     r13, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e9f0  test    eax, eax
0x18003e9f2  jns     short loc_18003EA1B
0x18003e9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e9fb  cmp     rcx, r14
0x18003e9fe  jz      loc_18003EC6D
0x18003ea04  test    byte ptr [rcx+1Ch], 2
0x18003ea08  jz      loc_18003EC6D
0x18003ea0e  lea     edx, [r12+1Dh]
0x18003ea13  mov     r8, r13
0x18003ea16  jmp     loc_18003EC61
0x18003ea1b  mov     rcx, [r15+50h]
0x18003ea1f  mov     rax, [rcx]
0x18003ea22  mov     r8d, 104h
0x18003ea28  lea     rdx, [rsp+2C0h+var_250]
0x18003ea2d  mov     rax, [rax+60h]
0x18003ea31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea36  mov     ebx, eax
0x18003ea38  test    eax, eax
0x18003ea3a  jns     short loc_18003EA6F
0x18003ea3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea43  cmp     rcx, r14
0x18003ea46  jz      loc_18003EDC1
0x18003ea4c  test    byte ptr [rcx+1Ch], 2
0x18003ea50  jz      loc_18003EDC1
0x18003ea56  mov     edx, 1Eh
0x18003ea5b  mov     r9d, eax
0x18003ea5e  mov     r8, r13
0x18003ea61  mov     rcx, [rcx+10h]
0x18003ea65  call    WPP_SF_d
0x18003ea6a  jmp     loc_18003EDC1
0x18003ea6f  mov     rcx, [rdi+1178h]
0x18003ea76  mov     rdx, [rcx]
0x18003ea79  mov     eax, [rdi]
0x18003ea7b  and     al, 2
0x18003ea7d  neg     al
0x18003ea7f  sbb     r9d, r9d
0x18003ea82  and     r9d, 2
0x18003ea86  add     r9d, 6Eh ; 'n'
0x18003ea8a  mov     rax, [rdx+40h]
0x18003ea8e  lea     rdx, [rsp+2C0h+var_270]
0x18003ea93  mov     qword ptr [rsp+2C0h+var_288], rdx
0x18003ea98  lea     rdx, [rsp+2C0h+pv]
0x18003ea9d  mov     [rsp+2C0h+var_290], rdx
0x18003eaa2  mov     dword ptr [rsp+2C0h+var_298], r12d
0x18003eaa7  mov     dword ptr [rsp+2C0h+var_2A0], r9d
0x18003eaac  mov     r9d, 2
0x18003eab2  mov     r8, rsi
0x18003eab5  mov     rdx, rdi
0x18003eab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eabd  mov     ebx, eax
0x18003eabf  test    eax, eax
0x18003eac1  jns     short loc_18003EAE7
0x18003eac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eaca  cmp     rcx, r14
0x18003eacd  jz      loc_18003EC6D
0x18003ead3  test    byte ptr [rcx+1Ch], 2
0x18003ead7  jz      loc_18003EC6D
0x18003eadd  mov     edx, 1Fh
0x18003eae2  jmp     loc_18003EA13
0x18003eae7  mov     r13d, 800704C7h
0x18003eaed  cmp     [rdi+1168h], r12
0x18003eaf4  jnz     short loc_18003EB2E
0x18003eaf6  mov     rcx, [r15+28h]; this
0x18003eafa  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003eaff  mov     ebx, eax
0x18003eb01  call    cs:__imp_GetCurrentThreadId
0x18003eb07  lea     rcx, [rsp+2C0h+var_268]
0x18003eb0c  mov     [rsp+2C0h+var_298], rcx; struct IPortableDevice **
0x18003eb11  mov     dword ptr [rsp+2C0h+var_2A0], ebx; int
0x18003eb15  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003eb18  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003eb1b  mov     edx, eax; unsigned int
0x18003eb1d  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18003eb22  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003eb27  mov     ebx, eax
0x18003eb29  jmp     loc_18003EBE0
0x18003eb2e  mov     r14d, r12d
0x18003eb31  mov     esi, r12d
0x18003eb34  mov     rax, [rdi+1168h]
0x18003eb3b  cmp     [rax+68h], r12d
0x18003eb3f  jnz     short loc_18003EBB4
0x18003eb41  mov     rcx, [r15+28h]; this
0x18003eb45  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003eb4a  mov     ebx, eax
0x18003eb4c  call    cs:__imp_GetCurrentThreadId
0x18003eb52  lea     rcx, [rsp+2C0h+var_268]
0x18003eb57  mov     [rsp+2C0h+var_298], rcx; struct IPortableDevice **
0x18003eb5c  mov     dword ptr [rsp+2C0h+var_2A0], ebx; int
0x18003eb60  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003eb63  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003eb66  mov     edx, eax; unsigned int
0x18003eb68  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18003eb6d  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003eb72  mov     ebx, eax
0x18003eb74  cmp     eax, 800700AAh
0x18003eb79  jnz     short loc_18003EBB7
0x18003eb7b  test    r14d, r14d
0x18003eb7e  jnz     short loc_18003EB95
0x18003eb80  lea     eax, [r14+1]
0x18003eb84  mov     r14d, eax
0x18003eb87  mov     esi, eax
0x18003eb89  mov     rcx, [rdi+1168h]; this
0x18003eb90  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003eb95  mov     rax, [rdi+1168h]
0x18003eb9c  cmp     [rax+68h], r12d
0x18003eba0  jnz     short loc_18003EBB4
0x18003eba2  mov     ecx, 5DCh; dwMilliseconds
0x18003eba7  call    cs:__imp_Sleep
0x18003ebad  test    r14d, r14d
0x18003ebb0  jz      short loc_18003EBB7
0x18003ebb2  jmp     short loc_18003EB34
0x18003ebb4  mov     ebx, r13d
0x18003ebb7  test    esi, esi
0x18003ebb9  jz      short loc_18003EBC7
0x18003ebbb  mov     rcx, [rdi+1168h]; this
0x18003ebc2  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003ebc7  mov     rax, [rdi+1168h]
0x18003ebce  cmp     [rax+68h], r12d
0x18003ebd2  jz      short loc_18003EBD9
0x18003ebd4  mov     ebx, r13d
0x18003ebd7  jmp     short loc_18003EBE4
0x18003ebd9  lea     r14, WPP_GLOBAL_Control
0x18003ebe0  test    ebx, ebx
0x18003ebe2  jns     short loc_18003EC22
0x18003ebe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ebeb  lea     r13, WPP_GLOBAL_Control
0x18003ebf2  cmp     rcx, r13
0x18003ebf5  jz      loc_18003EDC8
0x18003ebfb  test    byte ptr [rcx+1Ch], 2
0x18003ebff  jz      loc_18003EDC8
0x18003ec05  mov     edx, 20h ; ' '
0x18003ec0a  mov     r9d, ebx
0x18003ec0d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ec14  mov     rcx, [rcx+10h]
0x18003ec18  call    WPP_SF_d
0x18003ec1d  jmp     loc_18003EDC8
0x18003ec22  mov     rcx, [rdi+1178h]
0x18003ec29  mov     rax, [rcx]
0x18003ec2c  mov     r8, [rsp+2C0h+var_268]
0x18003ec31  mov     rdx, rdi
0x18003ec34  mov     rax, [rax+48h]
0x18003ec38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec3d  mov     ebx, eax
0x18003ec3f  test    eax, eax
0x18003ec41  jns     short loc_18003EC87
0x18003ec43  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ec4a  cmp     rcx, r14
0x18003ec4d  jz      short loc_18003EC6D
0x18003ec4f  test    byte ptr [rcx+1Ch], 2
0x18003ec53  jz      short loc_18003EC6D
0x18003ec55  mov     edx, 21h ; '!'
0x18003ec5a  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ec61  mov     r9d, eax
0x18003ec64  mov     rcx, [rcx+10h]
0x18003ec68  call    WPP_SF_d
0x18003ec6d  mov     dword ptr [rsp+2C0h+var_2A0], r12d; int
0x18003ec72  mov     r9, rdi; struct COPY_THREAD_DATA *
0x18003ec75  xor     r8d, r8d; unsigned __int16 *
0x18003ec78  mov     edx, ebx; int
0x18003ec7a  mov     rcx, r15; this
0x18003ec7d  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003ec82  jmp     loc_18003EDC1
0x18003ec87  cmp     [rdi+1168h], r12
0x18003ec8e  jnz     short loc_18003ECDB
0x18003ec90  mov     rcx, [rsp+2C0h+var_268]
0x18003ec95  mov     rax, [rcx]
0x18003ec98  lea     rdx, [rsp+2C0h+var_260]
0x18003ec9d  mov     rax, [rax+28h]
0x18003eca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eca6  mov     ebx, eax
0x18003eca8  test    ebx, ebx
0x18003ecaa  jns     loc_18003ED72
0x18003ecb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ecb7  lea     r13, WPP_GLOBAL_Control
0x18003ecbe  cmp     rcx, r13
0x18003ecc1  jz      loc_18003EDC8
0x18003ecc7  test    byte ptr [rcx+1Ch], 2
0x18003eccb  jz      loc_18003EDC8
0x18003ecd1  mov     edx, 22h ; '"'
0x18003ecd6  jmp     loc_18003EC0A
0x18003ecdb  mov     r14d, r12d
0x18003ecde  mov     esi, r12d
0x18003ece1  mov     rax, [rdi+1168h]
0x18003ece8  cmp     [rax+68h], r12d
0x18003ecec  jnz     short loc_18003ED46
0x18003ecee  mov     rcx, [rsp+2C0h+var_268]
0x18003ecf3  mov     rax, [rcx]
0x18003ecf6  lea     rdx, [rsp+2C0h+var_260]
0x18003ecfb  mov     rax, [rax+28h]
0x18003ecff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed04  mov     ebx, eax
0x18003ed06  cmp     eax, 800700AAh
0x18003ed0b  jnz     short loc_18003ED49
0x18003ed0d  test    r14d, r14d
0x18003ed10  jnz     short loc_18003ED27
0x18003ed12  lea     eax, [r14+1]
0x18003ed16  mov     r14d, eax
0x18003ed19  mov     esi, eax
0x18003ed1b  mov     rcx, [rdi+1168h]; this
0x18003ed22  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003ed27  mov     rax, [rdi+1168h]
0x18003ed2e  cmp     [rax+68h], r12d
0x18003ed32  jnz     short loc_18003ED46
0x18003ed34  mov     ecx, 5DCh; dwMilliseconds
0x18003ed39  call    cs:__imp_Sleep
0x18003ed3f  test    r14d, r14d
0x18003ed42  jz      short loc_18003ED49
0x18003ed44  jmp     short loc_18003ECE1
0x18003ed46  mov     ebx, r13d
0x18003ed49  test    esi, esi
0x18003ed4b  jz      short loc_18003ED59
0x18003ed4d  mov     rcx, [rdi+1168h]; this
0x18003ed54  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003ed59  mov     rax, [rdi+1168h]
0x18003ed60  cmp     [rax+68h], r12d
0x18003ed64  jz      loc_18003ECA8
0x18003ed6a  mov     ebx, r13d
0x18003ed6d  jmp     loc_18003ECB0
0x18003ed72  mov     esi, r12d
0x18003ed75  cmp     esi, [rsp+2C0h+var_270]
0x18003ed79  jnb     short loc_18003EDC1
0x18003ed7b  mov     rax, [rsp+2C0h+var_260]
0x18003ed80  mov     r8, [r15+50h]
0x18003ed84  mov     ecx, esi
0x18003ed86  mov     [rsp+2C0h+var_280], rdi; struct COPY_THREAD_DATA *
0x18003ed8b  mov     [rsp+2C0h+var_288], r12d; int
0x18003ed90  mov     [rsp+2C0h+var_290], r12; unsigned __int16 *
0x18003ed95  mov     dword ptr [rsp+2C0h+var_298], r12d; int
0x18003ed9a  mov     [rsp+2C0h+var_2A0], rax; struct IPortableDeviceContent *
0x18003ed9f  mov     r9, [rsp+2C0h+var_268]; struct IPortableDevice *
0x18003eda4  mov     r8, [r8+40h]; struct _ITEMIDLIST *
0x18003eda8  mov     rdx, [rsp+2C0h+pv]
0x18003edad  mov     rdx, [rdx+rcx*8]; struct _ITEMIDLIST *
0x18003edb1  mov     rcx, r15; this
0x18003edb4  call    ?_DoInsert@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@HPEBGHPEAVCOPY_THREAD_DATA@@@Z; CContentDropTarget::_DoInsert(_ITEMIDLIST const *,_ITEMIDLIST const *,IPortableDevice *,IPortableDeviceContent *,int,ushort const *,int,COPY_THREAD_DATA *)
0x18003edb9  mov     ebx, eax
0x18003edbb  inc     esi
0x18003edbd  test    eax, eax
0x18003edbf  jns     short loc_18003ED75
0x18003edc1  lea     r13, WPP_GLOBAL_Control
0x18003edc8  mov     r8, [r15+50h]
0x18003edcc  xor     r9d, r9d; dwItem2
0x18003edcf  mov     r8, [r8+40h]; dwItem1
0x18003edd3  xor     edx, edx; uFlags
0x18003edd5  mov     ecx, 1000h; wEventId
0x18003edda  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18003eddf  mov     rcx, [r15+50h]
0x18003ede3  mov     rax, [rcx]
0x18003ede6  mov     rdx, [rcx+40h]
0x18003edea  mov     rax, [rax+0A0h]
0x18003edf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edf6  mov     r14d, [rsp+2C0h+var_270]
0x18003edfb  mov     rsi, [rsp+2C0h+pv]
0x18003ee00  mov     edi, r12d
0x18003ee03  test    r14d, r14d
0x18003ee06  jz      short loc_18003EE1B
0x18003ee08  mov     ecx, edi
0x18003ee0a  mov     rcx, [rsi+rcx*8]; pv
0x18003ee0e  call    cs:__imp_CoTaskMemFree
0x18003ee14  inc     edi
0x18003ee16  cmp     edi, r14d
0x18003ee19  jb      short loc_18003EE08
0x18003ee1b  mov     rcx, rsi; pv
0x18003ee1e  call    cs:__imp_CoTaskMemFree
0x18003ee24  test    ebx, ebx
0x18003ee26  jns     short loc_18003EE53
0x18003ee28  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee2f  cmp     rcx, r13
0x18003ee32  jz      short loc_18003EE53
  ... truncated ...
```
