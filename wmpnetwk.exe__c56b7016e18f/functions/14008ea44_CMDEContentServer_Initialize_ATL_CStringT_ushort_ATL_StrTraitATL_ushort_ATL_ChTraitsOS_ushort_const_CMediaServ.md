# CMDEContentServer::Initialize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,CMediaServer *,IMDEOpCenter *,_EVENT_DESCRIPTOR &)

- ea: `0x14008ea44`
- end: `0x14008f318`
- name: `?Initialize@CMDEContentServer@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAVCMediaServer@@PEAUIMDEOpCenter@@AEAU_EVENT_DESCRIPTOR@@@Z`
- size: `2260`
- prototype: `__int64 __usercall@<rax>(CMDEContentServer *this@<rcx>, struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140045348`

## callees

- `0x14000b3f0`
- `0x14000cb74`
- `0x140024688`
- `0x140036610`
- `0x14003f17c`
- `0x14004a834`
- `0x14008ea44`
- `0x1400907d4`
- `0x14009e010`

## import_xrefs

- `winmde!MFCreateNetVRoot` at `0x14008ead6`
- `winmde!MFCreateNetVRoot` at `0x14008ee74`
- `winmde!MFCreateNetVRoot` at `0x14008ead6`
- `winmde!MFCreateNetVRoot` at `0x14008ee74`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMDEContentServer::Initialize(
        CMDEContentServer *this,
        _QWORD *a2,
        __int64 a3,
        struct IUnknown *a4,
        struct _EVENT_DESCRIPTOR *a5)
{
  _QWORD *v9; // rsi
  int v10; // eax
  int v11; // ebx
  struct _EVENT_DESCRIPTOR *v12; // rdi
  int v13; // eax
  int v14; // eax
  _QWORD *v15; // rsi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int MDEProfiles; // eax
  PVOID *v23; // r10
  __int128 v25; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+40h] [rbp-18h]
  __int64 v27; // [rsp+A0h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      *a2,
      a3,
      (char)a4);
  }
  *((_QWORD *)this + 57) = a3;
  if ( *((struct IUnknown **)this + 15) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 15, a4);
  ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)this + 58, a2);
  v9 = (_QWORD *)((char *)this + 144);
  v10 = MFCreateNetVRoot((char *)this + 144);
  v11 = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v10);
  }
  v12 = a5;
  *a5 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  if ( v11 < 0 )
    goto LABEL_98;
  v27 = 0;
  v13 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v9)(
          *v9,
          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
          &v27);
  v11 = v13;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v13 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v13);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  if ( v11 >= 0 )
  {
    v25 = 0;
    v26 = 0;
    LOWORD(v25) = 19;
    DWORD2(v25) = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v27 + 48LL))(
            v27,
            qword_1400BF698,
            &v25);
    v11 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v14 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v14);
    }
    *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  if ( v11 < 0 )
    goto LABEL_98;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 24LL))(*v9, 9519, (char *)this + 64);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 24LL))(*v9, 9520, (char *)this + 72);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 24LL))(*v9, 9521, (char *)this + 80);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 24LL))(*v9, 9522, (char *)this + 88);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 24LL))(*v9, 9531, (char *)this + 104);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v15 = (_QWORD *)((char *)this + 136);
  v11 = MFCreateNetVRoot((char *)this + 136);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  if ( v11 < 0 )
    goto LABEL_98;
  v27 = 0;
  v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v15)(
          *v15,
          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
          &v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v11);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  if ( v11 >= 0 )
  {
    v25 = 0;
    v26 = 0;
    LOWORD(v25) = 19;
    DWORD2(v25) = 2;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v27 + 48LL))(
            v27,
            qword_1400BF698,
            &v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v11);
    }
    *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  if ( v11 < 0 )
    goto LABEL_98;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9519, (char *)this + 64);
  v11 = v16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v16 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v16);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9520, (char *)this + 72);
  v11 = v17;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v17 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v17);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9521, (char *)this + 80);
  v11 = v18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v18 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v18);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9522, (char *)this + 88);
  v11 = v19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v19 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v19);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9526, (char *)this + 96);
  v11 = v20;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v20 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v20);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v15 + 24LL))(*v15, 9531, (char *)this + 104);
  v11 = v21;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v21 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v21);
  }
  *v12 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE;
  if ( v11 < 0 )
    goto LABEL_98;
  MDEProfiles = CMDEContentServer::CreateMDEProfiles(this, v12);
  v11 = MDEProfiles;
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((MDEProfiles >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)MDEProfiles);
LABEL_98:
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v23 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v23 + 28) & 1) != 0
    && *((unsigned __int8 *)v23 + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_Dd(v23[2], 41, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14008ea44  push    rbp
0x14008ea46  push    rbx
0x14008ea47  push    rsi
0x14008ea48  push    rdi
0x14008ea49  push    r12
0x14008ea4b  push    r13
0x14008ea4d  push    r14
0x14008ea4f  push    r15
0x14008ea51  mov     rbp, rsp
0x14008ea54  sub     rsp, 58h
0x14008ea58  mov     rbx, r9
0x14008ea5b  mov     rdi, r8
0x14008ea5e  mov     rsi, rdx
0x14008ea61  mov     r14, rcx
0x14008ea64  lea     r15, WPP_GLOBAL_Control
0x14008ea6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ea72  cmp     rcx, r15
0x14008ea75  jz      short loc_14008EAA5
0x14008ea77  test    byte ptr [rcx+1Ch], 1
0x14008ea7b  jz      short loc_14008EAA5
0x14008ea7d  cmp     byte ptr [rcx+19h], 5
0x14008ea81  jb      short loc_14008EAA5
0x14008ea83  mov     edx, 16h
0x14008ea88  mov     [rsp+58h+var_30], rbx
0x14008ea8d  mov     [rsp+58h+var_38], r8
0x14008ea92  mov     r9, [rsi]
0x14008ea95  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ea9c  mov     rcx, [rcx+10h]
0x14008eaa0  call    WPP_SF_Sqq
0x14008eaa5  mov     [r14+1C8h], rdi
0x14008eaac  lea     rcx, [r14+78h]; struct IUnknown **
0x14008eab0  cmp     [rcx], rbx
0x14008eab3  jz      short loc_14008EABD
0x14008eab5  mov     rdx, rbx; struct IUnknown *
0x14008eab8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14008eabd  lea     rcx, [r14+1D0h]
0x14008eac4  mov     rdx, rsi
0x14008eac7  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14008eacc  lea     rsi, [r14+90h]
0x14008ead3  mov     rcx, rsi
0x14008ead6  call    cs:__imp_MFCreateNetVRoot
0x14008eadc  mov     ebx, eax
0x14008eade  mov     r13d, 2
0x14008eae4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eaeb  cmp     rcx, r15
0x14008eaee  jz      short loc_14008EB20
0x14008eaf0  test    [rcx+1Ch], r13b
0x14008eaf4  jz      short loc_14008EB20
0x14008eaf6  mov     edx, eax
0x14008eaf8  sar     edx, 1Fh
0x14008eafb  and     edx, 0FFFFFFFDh
0x14008eafe  add     edx, 5
0x14008eb01  movzx   eax, byte ptr [rcx+19h]
0x14008eb05  cmp     eax, edx
0x14008eb07  jb      short loc_14008EB20
0x14008eb09  lea     edx, [r13+15h]
0x14008eb0d  mov     r9d, ebx
0x14008eb10  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008eb17  mov     rcx, [rcx+10h]
0x14008eb1b  call    WPP_SF_d
0x14008eb20  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT
0x14008eb27  mov     rdi, [rbp+arg_20]
0x14008eb2b  movdqu  xmmword ptr [rdi], xmm0
0x14008eb2f  test    ebx, ebx
0x14008eb31  js      loc_14008F2BF
0x14008eb37  mov     [rbp+arg_0], 0
0x14008eb3f  mov     rcx, [rsi]
0x14008eb42  mov     rax, [rcx]
0x14008eb45  lea     r8, [rbp+arg_0]
0x14008eb49  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x14008eb50  mov     rax, [rax]
0x14008eb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008eb58  mov     ebx, eax
0x14008eb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eb61  cmp     rcx, r15
0x14008eb64  jz      short loc_14008EB97
0x14008eb66  test    [rcx+1Ch], r13b
0x14008eb6a  jz      short loc_14008EB97
0x14008eb6c  mov     edx, eax
0x14008eb6e  sar     edx, 1Fh
0x14008eb71  and     edx, 0FFFFFFFDh
0x14008eb74  add     edx, 5
0x14008eb77  movzx   eax, byte ptr [rcx+19h]
0x14008eb7b  cmp     eax, edx
0x14008eb7d  jb      short loc_14008EB97
0x14008eb7f  mov     edx, 18h
0x14008eb84  mov     r9d, ebx
0x14008eb87  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008eb8e  mov     rcx, [rcx+10h]
0x14008eb92  call    WPP_SF_d
0x14008eb97  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT
0x14008eb9e  movdqu  xmmword ptr [rdi], xmm0
0x14008eba2  mov     ecx, 13h
0x14008eba7  test    ebx, ebx
0x14008eba9  js      short loc_14008EC24
0x14008ebab  xorps   xmm0, xmm0
0x14008ebae  xor     eax, eax
0x14008ebb0  movups  [rbp+var_28], xmm0
0x14008ebb4  mov     [rbp+var_18], rax
0x14008ebb8  mov     word ptr [rbp+var_28], cx
0x14008ebbc  mov     dword ptr [rbp+var_28+8], eax
0x14008ebbf  mov     rcx, [rbp+arg_0]
0x14008ebc3  mov     rax, [rcx]
0x14008ebc6  lea     r8, [rbp+var_28]
0x14008ebca  lea     rdx, qword_1400BF698
0x14008ebd1  mov     rax, [rax+30h]
0x14008ebd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ebda  mov     ebx, eax
0x14008ebdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ebe3  cmp     rcx, r15
0x14008ebe6  jz      short loc_14008EC19
0x14008ebe8  test    [rcx+1Ch], r13b
0x14008ebec  jz      short loc_14008EC19
0x14008ebee  mov     edx, eax
0x14008ebf0  sar     edx, 1Fh
0x14008ebf3  and     edx, 0FFFFFFFDh
0x14008ebf6  add     edx, 5
0x14008ebf9  movzx   eax, byte ptr [rcx+19h]
0x14008ebfd  cmp     eax, edx
0x14008ebff  jb      short loc_14008EC19
0x14008ec01  mov     edx, 19h
0x14008ec06  mov     r9d, ebx
0x14008ec09  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ec10  mov     rcx, [rcx+10h]
0x14008ec14  call    WPP_SF_d
0x14008ec19  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT
0x14008ec20  movdqu  xmmword ptr [rdi], xmm0
0x14008ec24  lea     rcx, [rbp+arg_0]
0x14008ec28  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008ec2d  test    ebx, ebx
0x14008ec2f  js      loc_14008F2BF
0x14008ec35  mov     rcx, [rsi]
0x14008ec38  mov     rax, [rcx]
0x14008ec3b  lea     r8, [r14+40h]
0x14008ec3f  mov     edx, 252Fh
0x14008ec44  mov     rax, [rax+18h]
0x14008ec48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ec4d  mov     ebx, eax
0x14008ec4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ec56  lea     rax, WPP_GLOBAL_Control
0x14008ec5d  cmp     rcx, rax
0x14008ec60  jz      short loc_14008EC93
0x14008ec62  test    [rcx+1Ch], r13b
0x14008ec66  jz      short loc_14008EC93
0x14008ec68  mov     edx, ebx
0x14008ec6a  sar     edx, 1Fh
0x14008ec6d  and     edx, 0FFFFFFFDh
0x14008ec70  add     edx, 5
0x14008ec73  movzx   eax, byte ptr [rcx+19h]
0x14008ec77  cmp     eax, edx
0x14008ec79  jb      short loc_14008EC93
0x14008ec7b  mov     edx, 1Ah
0x14008ec80  mov     r9d, ebx
0x14008ec83  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ec8a  mov     rcx, [rcx+10h]
0x14008ec8e  call    WPP_SF_d
0x14008ec93  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE
0x14008ec9a  movdqu  xmmword ptr [rdi], xmm0
0x14008ec9e  test    ebx, ebx
0x14008eca0  js      loc_14008F2B8
0x14008eca6  mov     rcx, [rsi]
0x14008eca9  mov     rax, [rcx]
0x14008ecac  lea     r8, [r14+48h]
0x14008ecb0  mov     edx, 2530h
0x14008ecb5  mov     rax, [rax+18h]
0x14008ecb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ecbe  mov     ebx, eax
0x14008ecc0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ecc7  lea     rax, WPP_GLOBAL_Control
0x14008ecce  cmp     rcx, rax
0x14008ecd1  jz      short loc_14008ED04
0x14008ecd3  test    [rcx+1Ch], r13b
0x14008ecd7  jz      short loc_14008ED04
0x14008ecd9  mov     edx, ebx
0x14008ecdb  sar     edx, 1Fh
0x14008ecde  and     edx, 0FFFFFFFDh
0x14008ece1  add     edx, 5
0x14008ece4  movzx   eax, byte ptr [rcx+19h]
0x14008ece8  cmp     eax, edx
0x14008ecea  jb      short loc_14008ED04
0x14008ecec  mov     edx, 1Bh
0x14008ecf1  mov     r9d, ebx
0x14008ecf4  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ecfb  mov     rcx, [rcx+10h]
0x14008ecff  call    WPP_SF_d
0x14008ed04  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE
0x14008ed0b  movdqu  xmmword ptr [rdi], xmm0
0x14008ed0f  test    ebx, ebx
0x14008ed11  js      loc_14008F2B8
0x14008ed17  mov     rcx, [rsi]
0x14008ed1a  lea     r8, [r14+50h]
0x14008ed1e  mov     rax, [rcx]
0x14008ed21  mov     edx, 2531h
0x14008ed26  mov     rax, [rax+18h]
0x14008ed2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ed2f  mov     ebx, eax
0x14008ed31  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ed38  lea     rax, WPP_GLOBAL_Control
0x14008ed3f  cmp     rcx, rax
0x14008ed42  jz      short loc_14008ED75
0x14008ed44  test    [rcx+1Ch], r13b
0x14008ed48  jz      short loc_14008ED75
0x14008ed4a  mov     edx, ebx
0x14008ed4c  sar     edx, 1Fh
0x14008ed4f  and     edx, 0FFFFFFFDh
0x14008ed52  add     edx, 5
0x14008ed55  movzx   eax, byte ptr [rcx+19h]
0x14008ed59  cmp     eax, edx
0x14008ed5b  jb      short loc_14008ED75
0x14008ed5d  mov     edx, 1Ch
0x14008ed62  mov     r9d, ebx
0x14008ed65  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ed6c  mov     rcx, [rcx+10h]
0x14008ed70  call    WPP_SF_d
0x14008ed75  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE
0x14008ed7c  movdqu  xmmword ptr [rdi], xmm0
0x14008ed80  test    ebx, ebx
0x14008ed82  js      loc_14008F2B8
0x14008ed88  mov     rcx, [rsi]
0x14008ed8b  mov     rax, [rcx]
0x14008ed8e  lea     r8, [r14+58h]
0x14008ed92  mov     edx, 2532h
0x14008ed97  mov     rax, [rax+18h]
0x14008ed9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008eda0  mov     ebx, eax
0x14008eda2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eda9  lea     rax, WPP_GLOBAL_Control
0x14008edb0  cmp     rcx, rax
0x14008edb3  jz      short loc_14008EDE6
0x14008edb5  test    byte ptr [rcx+1Ch], 2
0x14008edb9  jz      short loc_14008EDE6
0x14008edbb  mov     edx, ebx
0x14008edbd  sar     edx, 1Fh
0x14008edc0  and     edx, 0FFFFFFFDh
0x14008edc3  add     edx, 5
0x14008edc6  movzx   eax, byte ptr [rcx+19h]
0x14008edca  cmp     eax, edx
0x14008edcc  jb      short loc_14008EDE6
0x14008edce  mov     edx, 1Dh
0x14008edd3  mov     r9d, ebx
0x14008edd6  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008eddd  mov     rcx, [rcx+10h]
0x14008ede1  call    WPP_SF_d
0x14008ede6  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE
0x14008eded  movdqu  xmmword ptr [rdi], xmm0
0x14008edf1  test    ebx, ebx
0x14008edf3  js      loc_14008F2B8
0x14008edf9  mov     rcx, [rsi]
0x14008edfc  lea     r8, [r14+68h]
0x14008ee00  mov     rax, [rcx]
0x14008ee03  mov     edx, 253Bh
0x14008ee08  mov     rax, [rax+18h]
0x14008ee0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ee11  mov     ebx, eax
0x14008ee13  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ee1a  lea     rax, WPP_GLOBAL_Control
0x14008ee21  cmp     rcx, rax
0x14008ee24  jz      short loc_14008EE57
0x14008ee26  test    byte ptr [rcx+1Ch], 2
0x14008ee2a  jz      short loc_14008EE57
0x14008ee2c  mov     edx, ebx
0x14008ee2e  sar     edx, 1Fh
0x14008ee31  and     edx, 0FFFFFFFDh
0x14008ee34  add     edx, 5
0x14008ee37  movzx   eax, byte ptr [rcx+19h]
0x14008ee3b  cmp     eax, edx
0x14008ee3d  jb      short loc_14008EE57
0x14008ee3f  mov     edx, 1Eh
0x14008ee44  mov     r9d, ebx
0x14008ee47  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ee4e  mov     rcx, [rcx+10h]
0x14008ee52  call    WPP_SF_d
0x14008ee57  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_REGISTERDELEGATE
0x14008ee5e  movdqu  xmmword ptr [rdi], xmm0
0x14008ee62  test    ebx, ebx
0x14008ee64  js      loc_14008F2B8
0x14008ee6a  lea     rsi, [r14+88h]
0x14008ee71  mov     rcx, rsi
0x14008ee74  call    cs:__imp_MFCreateNetVRoot
0x14008ee7a  mov     ebx, eax
0x14008ee7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ee83  lea     rax, WPP_GLOBAL_Control
0x14008ee8a  cmp     rcx, rax
0x14008ee8d  jz      short loc_14008EEC0
0x14008ee8f  test    byte ptr [rcx+1Ch], 2
0x14008ee93  jz      short loc_14008EEC0
0x14008ee95  mov     edx, ebx
0x14008ee97  sar     edx, 1Fh
0x14008ee9a  and     edx, 0FFFFFFFDh
0x14008ee9d  add     edx, 5
0x14008eea0  movzx   eax, byte ptr [rcx+19h]
0x14008eea4  cmp     eax, edx
0x14008eea6  jb      short loc_14008EEC0
0x14008eea8  mov     edx, 1Fh
0x14008eead  mov     r9d, ebx
0x14008eeb0  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008eeb7  mov     rcx, [rcx+10h]
0x14008eebb  call    WPP_SF_d
0x14008eec0  movups  xmm0, cs:WMC_E_SERVICE_FAILED_MDECS_MFCREATENETVROOT
0x14008eec7  movdqu  xmmword ptr [rdi], xmm0
  ... truncated ...
```
