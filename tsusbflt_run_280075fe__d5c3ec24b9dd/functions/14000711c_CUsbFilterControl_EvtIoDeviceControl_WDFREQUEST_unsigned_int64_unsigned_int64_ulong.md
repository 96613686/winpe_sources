# CUsbFilterControl::EvtIoDeviceControl(WDFREQUEST__ *,unsigned __int64,unsigned __int64,ulong)

- ea: `0x14000711c`
- end: `0x140007c1d`
- name: `?EvtIoDeviceControl@CUsbFilterControl@@QEAAXPEAUWDFREQUEST__@@_K1K@Z`
- size: `2817`
- prototype: `void __usercall(CUsbFilterControl *__hidden this@<rcx>, struct WDFREQUEST__ *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400095c0`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x1400065e8`
- `0x14000711c`
- `0x140008940`
- `0x14000a2e8`
- `0x14000a90c`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`

## pseudocode

```c
void __fastcall CUsbFilterControl::EvtIoDeviceControl(
        CUsbFilterControl *this,
        struct WDFREQUEST__ *a2,
        void *a3,
        unsigned __int64 a4,
        unsigned int a5)
{
  int v7; // r12d
  __int64 v9; // rax
  __int64 v10; // rax
  const unsigned __int16 *v11; // r15
  __int64 v12; // r14
  NTSTATUS v13; // ebx
  unsigned __int16 **v14; // r15
  __int64 v15; // rdx
  const wchar_t *v16; // r12
  size_t v17; // rdx
  unsigned __int64 v18; // r11
  __int64 v19; // rdx
  const wchar_t *v20; // rcx
  size_t v21; // r11
  unsigned int v22; // esi
  unsigned int v23; // ebx
  __int64 v24; // r14
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  int v27; // edx
  int v28; // r8d
  void *v29; // r9
  unsigned __int16 **v30; // rax
  __int128 v31; // xmm0
  unsigned __int16 **v32; // rsi
  __int64 v33; // rdx
  const wchar_t *v34; // r15
  size_t v35; // rdx
  unsigned __int64 v36; // r11
  __int64 v37; // rdx
  const wchar_t *v38; // rcx
  size_t v39; // r11
  unsigned int v40; // ebx
  unsigned int v41; // esi
  __int64 v42; // rax
  const wchar_t *v43; // rcx
  int v44; // edx
  int v45; // r8d
  unsigned int v46; // r12d
  _DWORD *v47; // rcx
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // esi
  __int64 v52; // rax
  __int64 v53; // r10
  size_t v54; // rax
  __int64 v55; // r8
  __int64 v56; // r11
  unsigned int v57; // ecx
  const unsigned __int16 *v58; // rdx
  int v59; // eax
  int v60; // ecx
  struct WDFFILEOBJECT__ *v61; // rax
  void *v62; // rsi
  unsigned __int16 ***v63; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v64; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v66; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v67; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v68; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v69; // [rsp+94h] [rbp-6Ch] BYREF
  size_t pcchLength; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v72; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v73; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v74; // [rsp+B8h] [rbp-48h]
  CUsbFilterControl *v75; // [rsp+C0h] [rbp-40h]
  _QWORD v76[9]; // [rsp+C8h] [rbp-38h] BYREF
  void *v77[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v78[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v79; // [rsp+130h] [rbp+30h] BYREF
  __int128 v80; // [rsp+140h] [rbp+40h]
  __int64 v81; // [rsp+150h] [rbp+50h]

  v65 = a4;
  v7 = (int)a3;
  v77[0] = a3;
  v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[138].Blink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v9,
          off_14000F178);
  v11 = 0;
  v71 = 0;
  v12 = v10;
  if ( a5 == 2245636 )
  {
    v67 = 0;
    v46 = 0;
    v64 = 0;
    v77[0] = 0;
    v66 = 0;
    v69 = 0;
    v68 = 0;
    if ( a4 )
    {
      v63 = &v64;
      v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              a2,
              12,
              &v67);
      if ( v13 < 0 )
        goto LABEL_99;
      v47 = v67;
      v48 = *v67;
      if ( *v67 == -1 )
      {
        v78[0] = 0;
        v75 = 0;
      }
      else
      {
        if ( v48 > (unsigned __int64)v64 - 12 )
          goto LABEL_9;
        v78[0] = (unsigned __int16 *)((char *)v67 + v48 + 12);
        v65 = (unsigned __int64)v64 - v48 - 12;
        v11 = 0;
        v13 = ValidateMultiStrings(v78[0], v65, &v66, &v65, (const unsigned __int16 ***)&v64);
        if ( v13 < 0 )
          goto LABEL_99;
        v47 = v67;
        v46 = v66;
        v75 = (CUsbFilterControl *)v65;
      }
      v49 = v47[1];
      if ( v49 == -1 )
      {
        v74 = 0;
        v73 = 0;
      }
      else
      {
        if ( v49 > (unsigned __int64)v64 - 12 )
          goto LABEL_9;
        v74 = (unsigned __int16 *)((char *)v47 + v49 + 12);
        v65 = (unsigned __int64)v64 - v49 - 12;
        v11 = 0;
        v13 = ValidateMultiStrings(v74, v65, &v69, &v65, (const unsigned __int16 ***)v63);
        if ( v13 < 0 )
          goto LABEL_99;
        v47 = v67;
        v73 = v65;
      }
      v50 = v47[2];
      if ( v50 == -1 )
      {
        v72 = 0;
      }
      else
      {
        if ( v50 > (unsigned __int64)v64 - 12 )
          goto LABEL_9;
        v11 = (const unsigned __int16 *)((char *)v47 + v50 + 12);
        v65 = (unsigned __int64)v64 - v50 - 12;
        v13 = ValidateMultiStrings(v11, v65, &v68, &v65, (const unsigned __int16 ***)v63);
        if ( v13 < 0 )
          goto LABEL_99;
        v72 = v65;
      }
      v51 = 0;
      for ( LODWORD(v65) = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
                             WPP_MAIN_CB.Queue.ListEntry.Blink,
                             *((_QWORD *)this + 2)); v51 < (unsigned int)v65; ++v51 )
      {
        v52 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                *((_QWORD *)this + 2),
                v51);
        v53 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                v52,
                off_14000F0B8);
        v66 = *(_DWORD *)(v53 + 64);
        if ( v66 )
        {
          v54 = *(_QWORD *)v12;
          v55 = 0;
          v56 = *(_QWORD *)(v53 + 8);
          v57 = v66;
          pcchLength = *(_QWORD *)v12;
          do
          {
            if ( v54 != v56 )
            {
              v58 = v11;
              do
              {
                v59 = *(const unsigned __int16 *)((char *)v58
                                                + *(_QWORD *)(*(_QWORD *)(v53 + 72) + 8 * v55)
                                                - (_QWORD)v11);
                v60 = *v58 - v59;
                if ( v60 )
                  break;
                ++v58;
              }
              while ( v59 );
              if ( !v60 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
                v13 = -1073741768;
                goto LABEL_99;
              }
              v54 = pcchLength;
              v57 = v66;
            }
            v55 = (unsigned int)(v55 + 1);
          }
          while ( (unsigned int)v55 < v57 );
        }
      }
      v61 = (struct WDFFILEOBJECT__ *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[138].Blink)(
                                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                                        a2);
      v13 = CUsbFilterControl::AllocateDeviceClaimCheckObject(
              v75,
              v61,
              *(struct _EPROCESS **)v12,
              v78[0],
              (unsigned __int64)v75,
              v46,
              v74,
              v73,
              v69,
              v11,
              v72,
              v68,
              v77);
      if ( v13 >= 0 )
      {
        v62 = v77[0];
        v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Blink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                *((_QWORD *)this + 2),
                v77[0]);
        if ( v13 >= 0 )
        {
          ++*((_DWORD *)this + 6);
          if ( *(_QWORD *)(v12 + 8) )
          {
            ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[8].Flink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              *((_QWORD *)this + 2));
            ++*((_DWORD *)this + 6);
          }
          *(_QWORD *)(v12 + 8) = v62;
          CUsbFilterControl::InvalidateAllBuses(this);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
              (unsigned int)v13);
          ((void (__fastcall *)(struct _LIST_ENTRY *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v62);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
          (unsigned int)v13);
      }
      goto LABEL_99;
    }
    if ( *(_QWORD *)(v10 + 8) )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[8].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *((_QWORD *)this + 2));
      ++*((_DWORD *)this + 6);
      *(_QWORD *)(v12 + 8) = 0;
    }
    CUsbFilterControl::InvalidateAllBuses(this);
    goto LABEL_31;
  }
  if ( a5 != 2245640 )
  {
    if ( a5 == 2245644 )
    {
      v64 = 0;
      v77[0] = 0;
      v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned __int16 ***, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              a2,
              16,
              &v64,
              v77);
      if ( v13 >= 0 )
      {
        v13 = 0;
        v31 = *(_OWORD *)(v12 + 16);
        v71 = 16;
        *(_OWORD *)v64 = v31;
      }
      goto LABEL_99;
    }
    if ( a5 != 2245648 )
    {
      if ( a5 != 2245656 )
      {
        v13 = -1073741808;
        goto LABEL_99;
      }
      v64 = 0;
      v67 = 0;
      v81 = 0;
      v79 = 0;
      v80 = 0;
      memset(v76, 0, sizeof(v76));
      *(_OWORD *)v78 = 0;
      v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned __int16 ***, _DWORD **))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              a2,
              12,
              &v64,
              &v67);
      if ( v13 < 0 )
      {
LABEL_99:
        ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          (unsigned int)v13,
          v71);
        return;
      }
      v14 = v64;
      v15 = *(unsigned int *)v64;
      if ( (unsigned int)(v15 + 12) <= (unsigned __int64)v67 )
      {
        v16 = (const wchar_t *)((char *)v64 + v15 + 12);
        if ( v16 )
        {
          v17 = ((unsigned __int64)v67 - v15 - 12) >> 1;
          if ( v17 <= 0x7FFFFFFF )
          {
            v13 = RtlStringLengthWorkerW(v16, v17, &pcchLength);
            if ( v13 < 0 )
              goto LABEL_99;
            v19 = *((unsigned int *)v14 + 1);
            if ( (unsigned int)(v19 + 12) <= v18 )
            {
              v20 = (const wchar_t *)((char *)v14 + v19 + 12);
              if ( v20 )
              {
                v21 = (v18 - (unsigned int)v19 - 12) >> 1;
                if ( v21 <= 0x7FFFFFFF )
                {
                  v13 = RtlStringLengthWorkerW(v20, v21, &pcchLength);
                  if ( v13 < 0 )
                    goto LABEL_99;
                  v22 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
                          WPP_MAIN_CB.Queue.ListEntry.Blink,
                          *((_QWORD *)this + 1));
                  v23 = 0;
                  if ( v22 )
                  {
                    while ( 1 )
                    {
                      v24 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                              WPP_MAIN_CB.Queue.ListEntry.Blink,
                              *((_QWORD *)this + 1),
                              v23);
                      v25 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                              WPP_MAIN_CB.Queue.ListEntry.Blink,
                              v24,
                              off_14000F040);
                      v26 = v16;
                      do
                      {
                        v27 = *(const wchar_t *)((char *)v26 + *(_QWORD *)(v25 + 8) - (_QWORD)v16);
                        v28 = *v26 - v27;
                        if ( v28 )
                          break;
                        ++v26;
                      }
                      while ( v27 );
                      if ( !v28 )
                        break;
                      if ( ++v23 >= v22 )
                        goto LABEL_9;
                    }
                    if ( v25 )
                    {
                      v81 = 0;
                      v79 = 0;
                      LOWORD(v79) = 40;
                      v80 = 0;
                      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                        a2,
                        &v79);
                      LODWORD(v76[2]) = v65;
                      LODWORD(v76[1]) = v77[0];
                      LOWORD(v76[0]) = 15;
                      LODWORD(v76[3]) = 2245656;
                      v76[4] = 0;
                      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                        a2,
                        v76);
                      v29 = v78;
                      v78[1] = 0;
                      v78[0] = (unsigned __int16 *)0x800000010LL;
                      goto LABEL_26;
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_9:
      v13 = -1073741811;
      goto LABEL_99;
    }
    v64 = 0;
    v77[0] = 0;
    v71 = 86;
    if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned __int16 ***, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2,
           86,
           &v64,
           v77) < 0 )
    {
      v13 = -2147483643;
      goto LABEL_99;
    }
    v30 = v64;
    *(_OWORD *)v64 = *(_OWORD *)L"USB\\ROOT_HUB";
    *((_OWORD *)v30 + 1) = *(_OWORD *)L"_HUB";
    *((_OWORD *)v30 + 2) = xmmword_14000E170;
    *((_OWORD *)v30 + 3) = xmmword_14000E180;
    *((_OWORD *)v30 + 4) = xmmword_14000E190;
    *(unsigned __int16 **)((char *)v30 + 78) = (unsigned __int16 *)57;
LABEL_31:
    v13 = 0;
    goto LABEL_99;
  }
  v64 = 0;
  v67 = 0;
  v81 = 0;
  v79 = 0;
  v80 = 0;
  memset(v76, 0, sizeof(v76));
  *(_OWORD *)v77 = 0;
  v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned __int16 ***, _DWORD **))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          8,
          &v64,
          &v67);
  if ( v13 < 0 )
    goto LABEL_99;
  v32 = v64;
  v33 = *(unsigned int *)v64;
  if ( (unsigned int)(v33 + 8) > (unsigned __int64)v67 )
    goto LABEL_9;
  v34 = (const wchar_t *)((char *)v64 + v33 + 8);
  if ( !v34 )
    goto LABEL_9;
  v35 = ((unsigned __int64)v67 - (unsigned int)v33 - 8) >> 1;
  if ( v35 > 0x7FFFFFFF )
    goto LABEL_9;
  v13 = RtlStringLengthWorkerW(v34, v35, &pcchLength);
  if ( v13 < 0 )
    goto LABEL_99;
  v37 = *((unsigned int *)v32 + 1);
  if ( (unsigned int)(v37 + 8) > v36 )
    goto LABEL_9;
  v38 = (const wchar_t *)((char *)v32 + v37 + 8);
  if ( !v38 )
    goto LABEL_9;
  v39 = (v36 - (unsigned int)v37 - 8) >> 1;
  if ( v39 > 0x7FFFFFFF )
    goto LABEL_9;
  v13 = RtlStringLengthWorkerW(v38, v39, &pcchLength);
  if ( v13 < 0 )
    goto LABEL_99;
  v40 = 0;
  v41 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          *((_QWORD *)this + 1));
  if ( !v41 )
    goto LABEL_9;
  while ( 1 )
  {
    v24 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            *((_QWORD *)this + 1),
            v40);
    v42 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v24,
            off_14000F040);
    v43 = v34;
    do
    {
      v44 = *(const wchar_t *)((char *)v43 + *(_QWORD *)(v42 + 8) - (_QWORD)v34);
      v45 = *v43 - v44;
      if ( v45 )
        break;
      ++v43;
    }
    while ( v44 );
    if ( !v45 )
      break;
    if ( ++v40 >= v41 )
      goto LABEL_9;
  }
  if ( !v42 )
    goto LABEL_9;
  v81 = 0;
  v79 = 0;
  LOWORD(v79) = 40;
  v80 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v79);
  LODWORD(v76[2]) = v65;
  LOWORD(v76[0]) = 15;
  LODWORD(v76[3]) = 2245640;
  LODWORD(v76[1]) = v7;
  v76[4] = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v76);
  v29 = v77;
  v77[1] = 0;
  v77[0] = (void *)0x800000010LL;
LABEL_26:
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          v24,
          v29) )
  {
    v13 = -2147483631;
    goto LABEL_99;
  }
}

```

## disassembly

```asm
0x14000711c  push    rbp
0x14000711e  push    rbx
0x14000711f  push    rsi
0x140007120  push    rdi
0x140007121  push    r12
0x140007123  push    r13
0x140007125  push    r14
0x140007127  push    r15
0x140007129  lea     rbp, [rsp-68h]
0x14000712e  sub     rsp, 168h
0x140007135  mov     rax, cs:__security_cookie
0x14000713c  xor     rax, rsp
0x14000713f  mov     [rbp+0A0h+var_48], rax
0x140007143  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000714a  mov     rbx, r9
0x14000714d  mov     rdi, rcx
0x140007150  mov     [rsp+1A0h+var_128], rbx
0x140007155  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000715c  mov     r12, r8
0x14000715f  mov     [rbp+0A0h+var_90], r8
0x140007163  mov     r13, rdx
0x140007166  mov     rax, [rax+8A8h]
0x14000716d  call    _guard_dispatch_icall
0x140007172  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140007179  mov     rdx, rax
0x14000717c  mov     r8, cs:off_14000F178
0x140007183  mov     rax, [rcx+650h]
0x14000718a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007191  call    _guard_dispatch_icall
0x140007196  mov     ecx, [rbp+0A0h+arg_20]
0x14000719c  xor     r15d, r15d
0x14000719f  mov     [rbp+0A0h+var_100], r15
0x1400071a3  mov     r14, rax
0x1400071a6  sub     ecx, 224404h
0x1400071ac  jz      loc_14000778F
0x1400071b2  sub     ecx, 4
0x1400071b5  jz      loc_140007549
0x1400071bb  sub     ecx, 4
0x1400071be  jz      loc_1400074E7
0x1400071c4  sub     ecx, 4
0x1400071c7  jz      loc_140007449
0x1400071cd  cmp     ecx, 8
0x1400071d0  jz      short loc_1400071DC
0x1400071d2  mov     ebx, 0C0000010h
0x1400071d7  jmp     loc_140007BD8
0x1400071dc  xor     eax, eax
0x1400071de  mov     [rsp+1A0h+var_130], r15
0x1400071e3  xorps   xmm0, xmm0
0x1400071e6  mov     [rbp+0A0h+var_118], r15
0x1400071ea  xor     edx, edx; Val
0x1400071ec  mov     [rbp+0A0h+var_50], rax
0x1400071f0  lea     rcx, [rbp+0A0h+var_D8]; void *
0x1400071f4  lea     r8d, [rax+48h]; Size
0x1400071f8  movups  [rbp+0A0h+var_70], xmm0
0x1400071fc  movups  [rbp+0A0h+var_60], xmm0
0x140007200  call    memset
0x140007205  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000720c  lea     rcx, [rbp+0A0h+var_118]
0x140007210  xorps   xmm0, xmm0
0x140007213  mov     [rsp+1A0h+var_180], rcx
0x140007218  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000721f  lea     r9, [rsp+1A0h+var_130]
0x140007224  movups  xmmword ptr [rbp+0A0h+var_80], xmm0
0x140007228  mov     rax, [rax+868h]
0x14000722f  mov     esi, 0Ch
0x140007234  mov     r8d, esi
0x140007237  mov     rdx, r13
0x14000723a  call    _guard_dispatch_icall
0x14000723f  mov     ebx, eax
0x140007241  test    eax, eax
0x140007243  js      loc_140007BD8
0x140007249  mov     r15, [rsp+1A0h+var_130]
0x14000724e  mov     r11, [rbp+0A0h+var_118]
0x140007252  mov     edx, [r15]
0x140007255  lea     ecx, [rdx+0Ch]
0x140007258  cmp     rcx, r11
0x14000725b  jbe     short loc_140007267
0x14000725d  mov     ebx, 0C000000Dh
0x140007262  jmp     loc_140007BD8
0x140007267  lea     r12, [r15+0Ch]
0x14000726b  mov     rax, rdx
0x14000726e  add     r12, rdx
0x140007271  jz      short loc_14000725D
0x140007273  mov     rdx, r11
0x140007276  mov     r14d, 7FFFFFFFh
0x14000727c  sub     rdx, rax
0x14000727f  sub     rdx, rsi
0x140007282  shr     rdx, 1; cchMax
0x140007285  cmp     rdx, r14
0x140007288  ja      short loc_14000725D
0x14000728a  lea     r8, [rbp+0A0h+pcchLength]; pcchLength
0x14000728e  mov     rcx, r12; psz
0x140007291  call    RtlStringLengthWorkerW
0x140007296  mov     ebx, eax
0x140007298  test    eax, eax
0x14000729a  js      loc_140007BD8
0x1400072a0  mov     edx, [r15+4]
0x1400072a4  lea     ecx, [rdx+0Ch]
0x1400072a7  cmp     rcx, r11
0x1400072aa  ja      short loc_14000725D
0x1400072ac  lea     rcx, [r15+0Ch]
0x1400072b0  mov     eax, edx
0x1400072b2  xor     r15d, r15d
0x1400072b5  add     rcx, rdx; psz
0x1400072b8  jz      short loc_14000725D
0x1400072ba  sub     r11, rax
0x1400072bd  sub     r11, rsi
0x1400072c0  shr     r11, 1
0x1400072c3  cmp     r11, r14
0x1400072c6  ja      short loc_14000725D
0x1400072c8  lea     r8, [rbp+0A0h+pcchLength]; pcchLength
0x1400072cc  mov     rdx, r11; cchMax
0x1400072cf  call    RtlStringLengthWorkerW
0x1400072d4  mov     ebx, eax
0x1400072d6  test    eax, eax
0x1400072d8  js      loc_140007BD8
0x1400072de  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400072e5  mov     rdx, [rdi+8]
0x1400072e9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400072f0  mov     rax, [rax+70h]
0x1400072f4  call    _guard_dispatch_icall
0x1400072f9  mov     esi, eax
0x1400072fb  mov     ebx, r15d
0x1400072fe  test    eax, eax
0x140007300  jz      loc_14000725D
0x140007306  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000730d  mov     r8d, ebx
0x140007310  mov     rdx, [rdi+8]
0x140007314  mov     rax, [rcx+90h]
0x14000731b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007322  call    _guard_dispatch_icall
0x140007327  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000732e  mov     r14, rax
0x140007331  mov     r8, cs:off_14000F040
0x140007338  mov     rdx, r14
0x14000733b  mov     rax, [rcx+650h]
0x140007342  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007349  call    _guard_dispatch_icall
0x14000734e  mov     rcx, r12
0x140007351  mov     r9, [rax+8]
0x140007355  sub     r9, r12
0x140007358  movzx   r8d, word ptr [rcx]
0x14000735c  movzx   edx, word ptr [rcx+r9]
0x140007361  sub     r8d, edx
0x140007364  jnz     short loc_14000736E
0x140007366  add     rcx, 2
0x14000736a  test    edx, edx
0x14000736c  jnz     short loc_140007358
0x14000736e  test    r8d, r8d
0x140007371  jz      short loc_14000737E
0x140007373  inc     ebx
0x140007375  cmp     ebx, esi
0x140007377  jb      short loc_140007306
0x140007379  jmp     loc_14000725D
0x14000737e  test    rax, rax
0x140007381  jz      loc_14000725D
0x140007387  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000738e  lea     r8, [rbp+0A0h+var_70]
0x140007392  xor     eax, eax
0x140007394  xorps   xmm0, xmm0
0x140007397  mov     [rbp+0A0h+var_50], rax
0x14000739b  movups  [rbp+0A0h+var_70], xmm0
0x14000739f  lea     edx, [rax+28h]
0x1400073a2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400073a9  mov     word ptr [rbp+0A0h+var_70], dx
0x1400073ad  mov     rdx, r13
0x1400073b0  movups  [rbp+0A0h+var_60], xmm0
0x1400073b4  mov     rax, [rax+850h]
0x1400073bb  call    _guard_dispatch_icall
0x1400073c0  mov     rax, [rsp+1A0h+var_128]
0x1400073c5  lea     r8, [rbp+0A0h+var_D8]
0x1400073c9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400073d0  mov     rdx, r13
0x1400073d3  mov     [rbp+0A0h+var_C8], eax
0x1400073d6  mov     rax, [rbp+0A0h+var_90]
0x1400073da  mov     [rbp+0A0h+var_D0], eax
0x1400073dd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400073e4  mov     [rbp+0A0h+var_D8], 0Fh
0x1400073ea  mov     [rbp+0A0h+var_C0], 224418h
0x1400073f1  mov     [rbp+0A0h+var_B8], r15
0x1400073f5  mov     rax, [rax+7E0h]
0x1400073fc  call    _guard_dispatch_icall
0x140007401  lea     r9, [rbp+0A0h+var_80]
0x140007405  mov     [rbp+0A0h+var_80+8], r15
0x140007409  mov     dword ptr [rbp+0A0h+var_80], 10h
0x140007410  mov     dword ptr [rbp+0A0h+var_80+4], 8
0x140007417  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000741e  mov     r8, r14
0x140007421  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007428  mov     rdx, r13
0x14000742b  mov     rax, [rax+7E8h]
0x140007432  call    _guard_dispatch_icall
0x140007437  test    al, al
0x140007439  jnz     loc_140007BFC
0x14000743f  mov     ebx, 80000011h
0x140007444  jmp     loc_140007BD8
0x140007449  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007450  lea     rdx, [rbp+0A0h+var_90]
0x140007454  mov     ecx, 56h ; 'V'
0x140007459  mov     [rsp+1A0h+var_130], r15
0x14000745e  mov     [rbp+0A0h+var_90], r15
0x140007462  lea     r9, [rsp+1A0h+var_130]
0x140007467  mov     [rbp+0A0h+var_100], rcx
0x14000746b  mov     r8d, ecx
0x14000746e  mov     rax, [rax+870h]
0x140007475  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000747c  mov     [rsp+1A0h+var_180], rdx
0x140007481  mov     rdx, r13
0x140007484  call    _guard_dispatch_icall
0x140007489  test    eax, eax
0x14000748b  jns     short loc_140007497
0x14000748d  mov     ebx, 80000005h
0x140007492  jmp     loc_140007BD8
0x140007497  movaps  xmm0, xmmword ptr cs:aUsbRootHub_0; "USB\\ROOT_HUB"
0x14000749e  mov     rax, [rsp+1A0h+var_130]
0x1400074a3  movups  xmmword ptr [rax], xmm0
0x1400074a6  movaps  xmm1, xmmword ptr cs:aUsbRootHub_0+10h; "_HUB"
0x1400074ad  movups  xmmword ptr [rax+10h], xmm1
0x1400074b1  movaps  xmm0, cs:xmmword_14000E170
0x1400074b8  movups  xmmword ptr [rax+20h], xmm0
0x1400074bc  movaps  xmm1, cs:xmmword_14000E180
0x1400074c3  movups  xmmword ptr [rax+30h], xmm1
0x1400074c7  movaps  xmm0, cs:xmmword_14000E190
0x1400074ce  movups  xmmword ptr [rax+40h], xmm0
0x1400074d2  movsd   xmm1, qword ptr cs:xmmword_14000E190+0Eh
0x1400074da  movsd   qword ptr [rax+4Eh], xmm1
0x1400074df  mov     ebx, r15d
0x1400074e2  jmp     loc_140007BD8
0x1400074e7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400074ee  lea     rcx, [rbp+0A0h+var_90]
0x1400074f2  mov     [rsp+1A0h+var_130], r15
0x1400074f7  lea     r9, [rsp+1A0h+var_130]
0x1400074fc  mov     [rbp+0A0h+var_90], r15
0x140007500  mov     r8d, 10h
0x140007506  mov     [rsp+1A0h+var_180], rcx
0x14000750b  mov     rdx, r13
0x14000750e  mov     rax, [rax+870h]
0x140007515  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000751c  call    _guard_dispatch_icall
0x140007521  mov     ebx, eax
0x140007523  test    eax, eax
0x140007525  js      loc_140007BD8
0x14000752b  mov     rax, [rsp+1A0h+var_130]
0x140007530  mov     ebx, r15d
0x140007533  movups  xmm0, xmmword ptr [r14+10h]
0x140007538  mov     [rbp+0A0h+var_100], 10h
0x140007540  movdqu  xmmword ptr [rax], xmm0
0x140007544  jmp     loc_140007BD8
0x140007549  xor     eax, eax
0x14000754b  mov     [rsp+1A0h+var_130], r15
0x140007550  xorps   xmm0, xmm0
0x140007553  mov     [rbp+0A0h+var_118], r15
0x140007557  xor     edx, edx; Val
0x140007559  mov     [rbp+0A0h+var_50], rax
0x14000755d  lea     rcx, [rbp+0A0h+var_D8]; void *
0x140007561  lea     r8d, [rax+48h]; Size
0x140007565  movups  [rbp+0A0h+var_70], xmm0
0x140007569  movups  [rbp+0A0h+var_60], xmm0
0x14000756d  call    memset
0x140007572  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007579  lea     rcx, [rbp+0A0h+var_118]
0x14000757d  xorps   xmm0, xmm0
0x140007580  mov     [rsp+1A0h+var_180], rcx
0x140007585  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000758c  lea     r9, [rsp+1A0h+var_130]
0x140007591  movups  xmmword ptr [rbp+0A0h+var_90], xmm0
0x140007595  mov     rax, [rax+868h]
0x14000759c  mov     r8d, 8
0x1400075a2  mov     rdx, r13
0x1400075a5  call    _guard_dispatch_icall
0x1400075aa  mov     ebx, eax
0x1400075ac  test    eax, eax
0x1400075ae  js      loc_140007BD8
0x1400075b4  mov     rsi, [rsp+1A0h+var_130]
0x1400075b9  mov     r11, [rbp+0A0h+var_118]
0x1400075bd  mov     edx, [rsi]
0x1400075bf  lea     ecx, [rdx+8]
0x1400075c2  cmp     rcx, r11
0x1400075c5  ja      loc_14000725D
0x1400075cb  lea     r15, [rsi+8]
0x1400075cf  mov     eax, edx
0x1400075d1  add     r15, rdx
0x1400075d4  jz      loc_14000725D
0x1400075da  mov     rdx, r11
0x1400075dd  mov     r14d, 7FFFFFFFh
0x1400075e3  sub     rdx, rax
0x1400075e6  sub     rdx, 8
0x1400075ea  shr     rdx, 1; cchMax
0x1400075ed  cmp     rdx, r14
0x1400075f0  ja      loc_14000725D
0x1400075f6  lea     r8, [rbp+0A0h+pcchLength]; pcchLength
0x1400075fa  mov     rcx, r15; psz
0x1400075fd  call    RtlStringLengthWorkerW
0x140007602  mov     ebx, eax
0x140007604  test    eax, eax
0x140007606  js      loc_140007BD8
0x14000760c  mov     edx, [rsi+4]
0x14000760f  lea     ecx, [rdx+8]
0x140007612  cmp     rcx, r11
0x140007615  ja      loc_14000725D
  ... truncated ...
```
