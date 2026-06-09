# CAppArrangementSingleTransitionTarget::_PrepareTaggingForImmediateStoryboard(IAppLayoutOperationItem *,ITemporaryAppVisual *)

- ea: `0x18051dbb0`
- end: `0x18051e177`
- name: `?_PrepareTaggingForImmediateStoryboard@CAppArrangementSingleTransitionTarget@@AEAAXPEAUIAppLayoutOperationItem@@PEAUITemporaryAppVisual@@@Z`
- size: `1479`
- prototype: `void __fastcall(CAppArrangementSingleTransitionTarget *__hidden this, struct IAppLayoutOperationItem *, struct ITemporaryAppVisual *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18051cdc0`

## callees

- `0x1800255d0`
- `0x180031200`
- `0x18009b964`
- `0x1801fe0e0`
- `0x18032407c`
- `0x18032415c`
- `0x180356360`
- `0x18051d80c`
- `0x18051d9a8`
- `0x18051dbb0`
- `0x18051e180`
- `0x1806fa010`

## import_xrefs

- `USER32!GetWindowMinimizeRect` at `0x18051e003`
- `USER32!GetWindowMinimizeRect` at `0x18051e003`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18051de68`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18051de68`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de81`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de8a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de94`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de9e`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de81`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de8a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de94`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18051de9e`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18051e015`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18051e015`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18051e032`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18051e047`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18051e032`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18051e047`

## pseudocode

```c
void __fastcall CAppArrangementSingleTransitionTarget::_PrepareTaggingForImmediateStoryboard(
        CAppArrangementSingleTransitionTarget *this,
        struct IAppLayoutOperationItem *a2,
        struct ITemporaryAppVisual *a3)
{
  __int64 v3; // rax
  int (__fastcall *v6)(struct IAppLayoutOperationItem *, GUID *, __int64); // rbx
  __int64 v7; // rax
  int v8; // eax
  bool v9; // zf
  __int128 v10; // xmm0
  int *v11; // r15
  int v12; // r13d
  __int128 *v13; // rsi
  int v14; // ecx
  int v15; // eax
  __int64 top; // rcx
  int v17; // ebx
  __int128 v18; // xmm0
  struct tagRECT *v19; // rcx
  __int128 v20; // xmm1
  const struct tagRECT *v21; // rdx
  const struct tagRECT *v22; // r8
  int v23; // edx
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  char v26; // r14
  int v27; // eax
  char v28; // dl
  int v29; // eax
  int IsThreadRTL; // eax
  int v31; // eax
  int v32; // eax
  __int128 v33; // xmm1
  __int64 v34; // rax
  unsigned __int8 v35; // r14
  int v36; // eax
  __int64 v37; // rcx
  __int128 *v38; // r15
  HMONITOR v39; // r13
  HMONITOR v40; // rax
  __int128 v41; // xmm0
  int v42; // r8d
  const struct tagRECT *v43; // rdx
  LONG right; // edx
  LONG bottom; // r8d
  char v46; // [rsp+30h] [rbp-40h] BYREF
  char v47; // [rsp+31h] [rbp-3Fh] BYREF
  char v48; // [rsp+32h] [rbp-3Eh]
  struct tagRECT v49; // [rsp+38h] [rbp-38h] BYREF
  __int64 v50; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT rcDst; // [rsp+50h] [rbp-20h] BYREF

  v3 = *(_QWORD *)a2;
  *(_QWORD *)&v49.left = a3;
  v50 = 0;
  v6 = *(int (__fastcall **)(struct IAppLayoutOperationItem *, GUID *, __int64))(v3 + 32);
  v7 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&v50);
  if ( v6(a2, &GUID_372e1d3b_38d3_42e4_a15b_8ab2b178f513, v7) >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 96LL))(a2);
    v9 = *(_QWORD *)&v49.left == 0;
    v10 = *(_OWORD *)((char *)this + 172);
    v11 = (int *)((char *)this + 72);
    v12 = v8;
    v13 = (__int128 *)((char *)this + 88);
    *(_OWORD *)((char *)this + 72) = v10;
    if ( !v9 )
      v10 = *(_OWORD *)((char *)this + 236);
    v14 = *((_DWORD *)this + 19);
    v15 = *v11;
    *v13 = v10;
    *((_DWORD *)this + 21) -= v14;
    *((_DWORD *)this + 19) -= v14;
    *((_DWORD *)this + 20) -= v15;
    *v11 = 0;
    MatchRectAspectRatio((struct tagRECT *)((char *)this + 72), (const struct tagRECT *)((char *)this + 88));
    switch ( v12 )
    {
      case 7:
        *((_DWORD *)this + 10) = 71;
        v17 = 697663488;
        goto LABEL_77;
      case 8:
        v36 = 72;
        v35 = 1;
        break;
      case 9:
        v35 = 0;
        v36 = 73;
        break;
      default:
        v17 = 696614912;
        if ( ((v12 - 2) & 0xFFFFFFF7) == 0 )
        {
          v32 = 45;
          v33 = *v13;
          *(_OWORD *)((char *)this + 104) = *(_OWORD *)v11;
          top = 84;
          if ( v12 != 2 )
            v32 = 84;
          *((_DWORD *)this + 10) = v32;
          v34 = *((_QWORD *)this + 35);
          *(_OWORD *)((char *)this + 120) = v33;
          if ( v34 )
          {
            *((_QWORD *)this + 8) = v34;
            *((_DWORD *)this + 12) = 0x4000;
          }
          goto LABEL_77;
        }
        if ( *((_DWORD *)this + 68) == 6 )
        {
          v18 = *(_OWORD *)v11;
          v19 = (struct tagRECT *)((char *)this + 104);
          *((_DWORD *)this + 10) = 44;
          v20 = *(_OWORD *)((char *)this + 188);
          v21 = (const struct tagRECT *)((char *)this + 120);
          *(_OWORD *)((char *)this + 104) = v18;
          *(_OWORD *)((char *)this + 120) = v20;
LABEL_14:
          MatchRectAspectRatio(v19, v21);
          goto LABEL_77;
        }
        if ( CAppArrangementSingleTransitionTarget::_IsDragVisual(this)
          && (*(unsigned int (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 88LL))(a2) )
        {
          *((_DWORD *)this + 10) = 35;
          s_ComputeDragVisualDestinationRect((char *)this + 188, (char *)this + 88, (char *)this + 120);
          v19 = (struct tagRECT *)((char *)this + 104);
          v21 = v22;
          *(_OWORD *)((char *)this + 104) = *(_OWORD *)v11;
          goto LABEL_14;
        }
        if ( (*(unsigned int (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 80LL))(a2)
          && (*(unsigned int (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 88LL))(a2) )
        {
          if ( (unsigned __int8)Geometry::operator==((char *)this + 172, (char *)this + 188)
            || (v48 = 0, *(_QWORD *)&v49.left) )
          {
            v48 = 1;
          }
          v46 = 1;
          v47 = 1;
          s_GetAlignedRectsForApp(
            (_DWORD)this + 172,
            v23,
            (_DWORD)this + 104,
            (_DWORD)this + 120,
            (__int64)&v46,
            (__int64)&v47);
          if ( !v46 )
            v17 = 696549376;
          if ( !v47 )
            v17 &= ~0x8000u;
          if ( v48 )
          {
            v24 = *(_OWORD *)((char *)this + 120);
            v25 = *(_OWORD *)((char *)this + 104);
            *((_DWORD *)this + 10) = 28;
            *v13 = v24;
            *(_OWORD *)v11 = v25;
            if ( (unsigned __int8)Geometry::operator==((char *)this + 172, (char *)this + 188) )
              v17 = v17 & 0xDFDFFFFF | 0x200000;
          }
          else
          {
            *((_DWORD *)this + 10) = 23;
          }
          goto LABEL_77;
        }
        if ( !(*(unsigned int (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 80LL))(a2)
          || (*(unsigned int (__fastcall **)(struct IAppLayoutOperationItem *))(*(_QWORD *)a2 + 88LL))(a2) )
        {
LABEL_77:
          *((_DWORD *)this + 11) = CAppTransitionTargetBase::_GetDwmTargetFlag(
                                     (CAppTransitionTargetBase *)top,
                                     *((HWND *)this + 7),
                                     0,
                                     v17);
          goto LABEL_78;
        }
        v26 = 1;
        rcDst = 0;
        if ( *((_DWORD *)this + 68) == 1
          && !IntersectRect(&rcDst, (const RECT *)((char *)this + 88), (const RECT *)((char *)this + 136)) )
        {
          *((_DWORD *)this + 10) = 43;
          v17 = 671449088;
          SetRectEmpty((LPRECT)((char *)this + 72));
          SetRectEmpty((LPRECT)((char *)this + 88));
          SetRectEmpty((LPRECT)((char *)this + 104));
          SetRectEmpty((LPRECT)((char *)this + 120));
          goto LABEL_77;
        }
        if ( (unsigned int)(v12 - 3) <= 1 || (*((_BYTE *)this + 160) & 0x18) != 0 )
        {
          v29 = *((_DWORD *)this + 40);
          v28 = 1;
          if ( (v29 & 1) != 0 )
          {
            *((_DWORD *)this + 10) = 7;
          }
          else if ( (v29 & 4) != 0 )
          {
            *((_DWORD *)this + 10) = 31;
          }
          else
          {
            *((_DWORD *)this + 10) = 23;
          }
        }
        else
        {
          v27 = 20;
          v28 = 0;
          if ( *((_DWORD *)this + 39) == 3 )
            v27 = 28;
          *((_DWORD *)this + 10) = v27;
        }
        *(_OWORD *)((char *)this + 120) = *v13;
        if ( !v28 )
        {
LABEL_54:
          *(_OWORD *)((char *)this + 104) = *(_OWORD *)v11;
          MatchRectAspectRatio((struct tagRECT *)((char *)this + 104), (const struct tagRECT *)((char *)this + 120));
          if ( *((_DWORD *)this + 68) )
            v17 &= ~0x20000000u;
          goto LABEL_77;
        }
        if ( (unsigned int)(v12 - 3) <= 1 )
        {
          IsThreadRTL = Mirror_IsThreadRTL();
          if ( v12 == 3 )
            goto LABEL_52;
          if ( v12 == 4 )
          {
LABEL_51:
            v31 = *((_DWORD *)this + 36);
LABEL_53:
            *((_DWORD *)this + 30) = v31;
            *((_DWORD *)this + 32) = *((_DWORD *)this + 24) + v31 - *(_DWORD *)v13;
            goto LABEL_54;
          }
          v26 = 0;
        }
        else
        {
          IsThreadRTL = Mirror_IsThreadRTL();
        }
        v17 = 696516608;
        if ( v26 && IsThreadRTL )
          goto LABEL_51;
LABEL_52:
        v31 = *(_DWORD *)v13 + *((_DWORD *)this + 34) - *((_DWORD *)this + 24);
        goto LABEL_53;
    }
    v37 = *((_QWORD *)this + 7);
    v17 = (v35 << 20) + 696614912;
    *((_DWORD *)this + 10) = v36;
    rcDst = 0;
    if ( !(unsigned int)GetWindowMinimizeRect(v37, &rcDst) || IsRectEmpty(&rcDst) )
    {
      if ( v12 == 8 )
        *((_DWORD *)this + 10) = 71;
      else
        *((_DWORD *)this + 10) = 4095;
      goto LABEL_77;
    }
    *(_OWORD *)((char *)this + 104) = *(_OWORD *)v11;
    v38 = (__int128 *)((char *)this + 188);
    v39 = MonitorFromRect(&rcDst, 0);
    v40 = MonitorFromRect((LPCRECT)((char *)this + 188), 0);
    if ( v35 || v40 && v40 == v39 )
    {
      v42 = (int)(float)((float)(rcDst.right - rcDst.left) * 0.60000002);
      v43 = (const struct tagRECT *)((char *)this + 188);
      v49.top = rcDst.top - v42 * (rcDst.bottom - rcDst.top) / (rcDst.right - rcDst.left);
      v49.bottom = rcDst.top;
      v49.left = (int)(float)((float)((float)v42 * 0.30000001) + (float)rcDst.left);
      v49.right = v42 + v49.left;
      if ( v35 )
        v43 = (const struct tagRECT *)((char *)this + 172);
      MatchRectAspectRatio(&v49, v43);
      top = (unsigned int)v49.top;
      right = v49.right;
      bottom = v49.bottom;
      if ( v35 )
      {
        *((_DWORD *)this + 30) = v49.left;
        *((_DWORD *)this + 31) = top;
        *((_DWORD *)this + 32) = right;
        *((_DWORD *)this + 33) = bottom;
        goto LABEL_77;
      }
      *(_DWORD *)v13 = v49.left;
      *((_DWORD *)this + 23) = top;
      *((_DWORD *)this + 24) = right;
      *((_DWORD *)this + 25) = bottom;
      v41 = *v38;
    }
    else
    {
      v41 = *v38;
      *((_DWORD *)this + 10) = 74;
      *v13 = v41;
    }
    *(_OWORD *)((char *)this + 120) = v41;
    goto LABEL_77;
  }
LABEL_78:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
}

```

## disassembly

```asm
0x18051dbb0  mov     [rsp-38h+arg_10], rbx
0x18051dbb5  push    rbp
0x18051dbb6  push    rsi
0x18051dbb7  push    rdi
0x18051dbb8  push    r12
0x18051dbba  push    r13
0x18051dbbc  push    r14
0x18051dbbe  push    r15
0x18051dbc0  mov     rbp, rsp
0x18051dbc3  sub     rsp, 70h
0x18051dbc7  mov     rax, cs:__security_cookie
0x18051dbce  xor     rax, rsp
0x18051dbd1  mov     [rbp+var_10], rax
0x18051dbd5  mov     rax, [rdx]
0x18051dbd8  mov     rdi, rcx
0x18051dbdb  lea     rcx, [rbp+var_28]
0x18051dbdf  mov     qword ptr [rbp+var_38.left], r8
0x18051dbe3  mov     r14, rdx
0x18051dbe6  mov     [rbp+var_28], 0
0x18051dbee  mov     rbx, [rax+20h]
0x18051dbf2  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>)
0x18051dbf7  mov     r8, rax
0x18051dbfa  lea     rdx, _GUID_372e1d3b_38d3_42e4_a15b_8ab2b178f513
0x18051dc01  mov     rax, rbx
0x18051dc04  mov     rcx, r14
0x18051dc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051dc0c  test    eax, eax
0x18051dc0e  js      loc_18051E14A
0x18051dc14  mov     rax, [r14]
0x18051dc17  mov     rcx, r14
0x18051dc1a  mov     rax, [rax+60h]
0x18051dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051dc23  cmp     qword ptr [rbp+var_38.left], 0
0x18051dc28  lea     r12, [rdi+0ACh]
0x18051dc2f  movups  xmm0, xmmword ptr [r12]
0x18051dc34  lea     r15, [rdi+48h]
0x18051dc38  mov     r13d, eax
0x18051dc3b  lea     rsi, [rdi+58h]
0x18051dc3f  movdqu  xmmword ptr [r15], xmm0
0x18051dc44  jz      short loc_18051DC4D
0x18051dc46  movups  xmm0, xmmword ptr [rdi+0ECh]
0x18051dc4d  mov     ecx, [rdi+4Ch]
0x18051dc50  mov     rdx, rsi; struct tagRECT *
0x18051dc53  mov     eax, [r15]
0x18051dc56  movdqu  xmmword ptr [rsi], xmm0
0x18051dc5a  sub     [r15+0Ch], ecx
0x18051dc5e  sub     [r15+4], ecx
0x18051dc62  mov     rcx, r15; struct tagRECT *
0x18051dc65  sub     [r15+8], eax
0x18051dc69  mov     dword ptr [r15], 0
0x18051dc70  call    ?MatchRectAspectRatio@@YAXPEAUtagRECT@@PEBU1@@Z; MatchRectAspectRatio(tagRECT *,tagRECT const *)
0x18051dc75  cmp     r13d, 7
0x18051dc79  jnz     short loc_18051DC8C
0x18051dc7b  mov     dword ptr [rdi+28h], 47h ; 'G'
0x18051dc82  mov     ebx, 29958000h
0x18051dc87  jmp     loc_18051E138
0x18051dc8c  cmp     r13d, 8
0x18051dc90  jz      loc_18051DFDB
0x18051dc96  cmp     r13d, 9
0x18051dc9a  jz      loc_18051DFD1
0x18051dca0  lea     eax, [r13-2]
0x18051dca4  mov     ebx, 29858000h
0x18051dca9  test    eax, 0FFFFFFF7h
0x18051dcae  jz      loc_18051DF8E
0x18051dcb4  cmp     dword ptr [rdi+110h], 6
0x18051dcbb  jnz     short loc_18051DCE1
0x18051dcbd  movups  xmm0, xmmword ptr [r15]
0x18051dcc1  lea     rcx, [rdi+68h]
0x18051dcc5  mov     dword ptr [rdi+28h], 2Ch ; ','
0x18051dccc  movups  xmm1, xmmword ptr [rdi+0BCh]
0x18051dcd3  lea     rdx, [rdi+78h]
0x18051dcd7  movdqu  xmmword ptr [rcx], xmm0
0x18051dcdb  movdqu  xmmword ptr [rdx], xmm1
0x18051dcdf  jmp     short loc_18051DD29
0x18051dce1  mov     rcx, rdi; this
0x18051dce4  call    ?_IsDragVisual@CAppArrangementSingleTransitionTarget@@AEBA_NXZ; CAppArrangementSingleTransitionTarget::_IsDragVisual(void)
0x18051dce9  test    al, al
0x18051dceb  jz      short loc_18051DD33
0x18051dced  mov     rax, [r14]
0x18051dcf0  mov     rcx, r14
0x18051dcf3  mov     rax, [rax+58h]
0x18051dcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051dcfc  test    eax, eax
0x18051dcfe  jz      short loc_18051DD33
0x18051dd00  lea     r8, [rdi+78h]
0x18051dd04  mov     dword ptr [rdi+28h], 23h ; '#'
0x18051dd0b  lea     rcx, [rdi+0BCh]
0x18051dd12  mov     rdx, rsi
0x18051dd15  call    s_ComputeDragVisualDestinationRect
0x18051dd1a  movups  xmm1, xmmword ptr [r15]
0x18051dd1e  lea     rcx, [rdi+68h]; struct tagRECT *
0x18051dd22  mov     rdx, r8; struct tagRECT *
0x18051dd25  movdqu  xmmword ptr [rcx], xmm1
0x18051dd29  call    ?MatchRectAspectRatio@@YAXPEAUtagRECT@@PEBU1@@Z; MatchRectAspectRatio(tagRECT *,tagRECT const *)
0x18051dd2e  jmp     loc_18051E138
0x18051dd33  mov     rax, [r14]
0x18051dd36  mov     rcx, r14
0x18051dd39  mov     rax, [rax+50h]
0x18051dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051dd42  test    eax, eax
0x18051dd44  jz      loc_18051DE18
0x18051dd4a  mov     rax, [r14]
0x18051dd4d  mov     rcx, r14
0x18051dd50  mov     rax, [rax+58h]
0x18051dd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051dd59  test    eax, eax
0x18051dd5b  jz      loc_18051DE18
0x18051dd61  lea     r13, [rdi+0BCh]
0x18051dd68  mov     rcx, r12
0x18051dd6b  mov     rdx, r13
0x18051dd6e  call    ??8Geometry@@YA_NAEBUCRect@0@0@Z; Geometry::operator==(Geometry::CRect const &,Geometry::CRect const &)
0x18051dd73  mov     r14d, 1
0x18051dd79  test    al, al
0x18051dd7b  jnz     short loc_18051DD87
0x18051dd7d  cmp     qword ptr [rbp+var_38.left], 0
0x18051dd82  mov     [rbp+var_3E], al
0x18051dd85  jz      short loc_18051DD8B
0x18051dd87  mov     [rbp+var_3E], r14b
0x18051dd8b  lea     rcx, [rbp+var_3F]
0x18051dd8f  mov     [rbp+var_40], r14b
0x18051dd93  mov     [rsp+70h+var_48], rcx
0x18051dd98  lea     r8, [rdi+68h]
0x18051dd9c  lea     rcx, [rbp+var_40]
0x18051dda0  mov     [rbp+var_3F], r14b
0x18051dda4  mov     [rsp+70h+var_50], rcx
0x18051dda9  lea     r9, [rdi+78h]
0x18051ddad  mov     rcx, r12
0x18051ddb0  call    s_GetAlignedRectsForApp
0x18051ddb5  xor     r8d, r8d
0x18051ddb8  mov     eax, 29848000h
0x18051ddbd  cmp     [rbp+var_40], r8b
0x18051ddc1  cmovz   ebx, eax
0x18051ddc4  cmp     [rbp+var_3F], r8b
0x18051ddc8  jnz     short loc_18051DDCE
0x18051ddca  btr     ebx, 0Fh
0x18051ddce  cmp     [rbp+var_3E], r8b
0x18051ddd2  jz      short loc_18051DE0C
0x18051ddd4  movups  xmm0, xmmword ptr [rdi+78h]
0x18051ddd8  mov     rdx, r13
0x18051dddb  mov     rcx, r12
0x18051ddde  movups  xmm1, xmmword ptr [rdi+68h]
0x18051dde2  mov     dword ptr [rdi+28h], 1Ch
0x18051dde9  movdqu  xmmword ptr [rsi], xmm0
0x18051dded  movdqu  xmmword ptr [r15], xmm1
0x18051ddf2  call    ??8Geometry@@YA_NAEBUCRect@0@0@Z; Geometry::operator==(Geometry::CRect const &,Geometry::CRect const &)
0x18051ddf7  test    al, al
0x18051ddf9  jz      loc_18051E138
0x18051ddff  btr     ebx, 1Dh
0x18051de03  bts     ebx, 15h
0x18051de07  jmp     loc_18051E138
0x18051de0c  mov     dword ptr [rdi+28h], 17h
0x18051de13  jmp     loc_18051E138
0x18051de18  mov     rax, [r14]
0x18051de1b  mov     rcx, r14
0x18051de1e  mov     rax, [rax+50h]
0x18051de22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051de27  test    eax, eax
0x18051de29  jz      loc_18051E138
0x18051de2f  mov     rax, [r14]
0x18051de32  mov     rcx, r14
0x18051de35  mov     rax, [rax+58h]
0x18051de39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051de3e  test    eax, eax
0x18051de40  jnz     loc_18051E138
0x18051de46  lea     r14d, [rax+1]
0x18051de4a  xorps   xmm0, xmm0
0x18051de4d  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x18051de51  cmp     [rdi+110h], r14d
0x18051de58  jnz     short loc_18051DEA9
0x18051de5a  lea     r8, [rdi+88h]; lprcSrc2
0x18051de61  mov     rdx, rsi; lprcSrc1
0x18051de64  lea     rcx, [rbp+rcDst]; lprcDst
0x18051de68  call    cs:__imp_IntersectRect
0x18051de6e  test    eax, eax
0x18051de70  jnz     short loc_18051DEA9
0x18051de72  mov     rcx, r15; lprc
0x18051de75  mov     dword ptr [rdi+28h], 2Bh ; '+'
0x18051de7c  mov     ebx, 28058000h
0x18051de81  call    cs:__imp_SetRectEmpty
0x18051de87  mov     rcx, rsi; lprc
0x18051de8a  call    cs:__imp_SetRectEmpty
0x18051de90  lea     rcx, [rdi+68h]; lprc
0x18051de94  call    cs:__imp_SetRectEmpty
0x18051de9a  lea     rcx, [rdi+78h]; lprc
0x18051de9e  call    cs:__imp_SetRectEmpty
0x18051dea4  jmp     loc_18051E138
0x18051dea9  lea     eax, [r13-3]
0x18051dead  cmp     eax, r14d
0x18051deb0  jbe     short loc_18051DED4
0x18051deb2  test    byte ptr [rdi+0A0h], 18h
0x18051deb9  jnz     short loc_18051DED4
0x18051debb  mov     eax, 14h
0x18051dec0  xor     dl, dl
0x18051dec2  cmp     dword ptr [rdi+9Ch], 3
0x18051dec9  lea     ecx, [rax+8]
0x18051decc  cmovz   eax, ecx
0x18051decf  mov     [rdi+28h], eax
0x18051ded2  jmp     short loc_18051DEFF
0x18051ded4  mov     eax, [rdi+0A0h]
0x18051deda  mov     dl, r14b
0x18051dedd  test    r14b, al
0x18051dee0  jz      short loc_18051DEEB
0x18051dee2  mov     dword ptr [rdi+28h], 7
0x18051dee9  jmp     short loc_18051DEFF
0x18051deeb  test    al, 4
0x18051deed  jz      short loc_18051DEF8
0x18051deef  mov     dword ptr [rdi+28h], 1Fh
0x18051def6  jmp     short loc_18051DEFF
0x18051def8  mov     dword ptr [rdi+28h], 17h
0x18051deff  lea     r12, [rdi+78h]
0x18051df03  movups  xmm0, xmmword ptr [rsi]
0x18051df06  movdqu  xmmword ptr [r12], xmm0
0x18051df0c  test    dl, dl
0x18051df0e  jz      short loc_18051DF64
0x18051df10  lea     eax, [r13-3]
0x18051df14  cmp     eax, r14d
0x18051df17  jbe     short loc_18051DF20
0x18051df19  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x18051df1e  jmp     short loc_18051DF34
0x18051df20  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x18051df25  cmp     r13d, 3
0x18051df29  jz      short loc_18051DF4A
0x18051df2b  cmp     r13d, 4
0x18051df2f  jz      short loc_18051DF42
0x18051df31  xor     r14b, r14b
0x18051df34  mov     ebx, 29840000h
0x18051df39  test    r14b, r14b
0x18051df3c  jz      short loc_18051DF4A
0x18051df3e  test    eax, eax
0x18051df40  jz      short loc_18051DF4A
0x18051df42  mov     eax, [rdi+90h]
0x18051df48  jmp     short loc_18051DF55
0x18051df4a  mov     eax, [rdi+88h]
0x18051df50  sub     eax, [rsi+8]
0x18051df53  add     eax, [rsi]
0x18051df55  mov     [r12], eax
0x18051df59  sub     eax, [rsi]
0x18051df5b  add     eax, [rsi+8]
0x18051df5e  mov     [rdi+80h], eax
0x18051df64  movups  xmm0, xmmword ptr [r15]
0x18051df68  lea     rcx, [rdi+68h]; struct tagRECT *
0x18051df6c  mov     rdx, r12; struct tagRECT *
0x18051df6f  movdqu  xmmword ptr [rcx], xmm0
0x18051df73  call    ?MatchRectAspectRatio@@YAXPEAUtagRECT@@PEBU1@@Z; MatchRectAspectRatio(tagRECT *,tagRECT const *)
0x18051df78  cmp     dword ptr [rdi+110h], 0
0x18051df7f  jz      loc_18051E138
0x18051df85  btr     ebx, 1Dh
0x18051df89  jmp     loc_18051E138
0x18051df8e  movups  xmm0, xmmword ptr [r15]
0x18051df92  mov     eax, 2Dh ; '-'
0x18051df97  cmp     r13d, 2
0x18051df9b  movups  xmm1, xmmword ptr [rsi]
0x18051df9e  movdqu  xmmword ptr [rdi+68h], xmm0
0x18051dfa3  lea     ecx, [rax+27h]
0x18051dfa6  cmovnz  eax, ecx
0x18051dfa9  mov     [rdi+28h], eax
0x18051dfac  mov     rax, [rdi+118h]
0x18051dfb3  movdqu  xmmword ptr [rdi+78h], xmm1
0x18051dfb8  test    rax, rax
0x18051dfbb  jz      loc_18051E138
0x18051dfc1  mov     [rdi+40h], rax
0x18051dfc5  mov     dword ptr [rdi+30h], 4000h
0x18051dfcc  jmp     loc_18051E138
0x18051dfd1  xor     r14b, r14b
0x18051dfd4  mov     eax, 49h ; 'I'
0x18051dfd9  jmp     short loc_18051DFE4
0x18051dfdb  mov     eax, 48h ; 'H'
0x18051dfe0  lea     r14d, [rax-47h]
0x18051dfe4  mov     rcx, [rdi+38h]
0x18051dfe8  lea     rdx, [rbp+rcDst]
0x18051dfec  xorps   xmm0, xmm0
0x18051dfef  movzx   ebx, r14b
0x18051dff3  shl     ebx, 14h
0x18051dff6  add     ebx, 29858000h
0x18051dffc  mov     [rdi+28h], eax
0x18051dfff  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x18051e003  call    cs:__imp_GetWindowMinimizeRect
0x18051e009  test    eax, eax
0x18051e00b  jz      loc_18051E122
0x18051e011  lea     rcx, [rbp+rcDst]; lprc
0x18051e015  call    cs:__imp_IsRectEmpty
0x18051e01b  test    eax, eax
0x18051e01d  jnz     loc_18051E122
0x18051e023  movups  xmm0, xmmword ptr [r15]
0x18051e027  xor     edx, edx; dwFlags
0x18051e029  lea     rcx, [rbp+rcDst]; lprc
0x18051e02d  movdqu  xmmword ptr [rdi+68h], xmm0
0x18051e032  call    cs:__imp_MonitorFromRect
0x18051e038  lea     r15, [rdi+0BCh]
0x18051e03f  xor     edx, edx; dwFlags
0x18051e041  mov     rcx, r15; lprc
0x18051e044  mov     r13, rax
0x18051e047  call    cs:__imp_MonitorFromRect
0x18051e04d  test    r14b, r14b
0x18051e050  jnz     short loc_18051E070
0x18051e052  test    rax, rax
0x18051e055  jz      short loc_18051E05C
0x18051e057  cmp     rax, r13
0x18051e05a  jz      short loc_18051E070
0x18051e05c  movups  xmm0, xmmword ptr [r15]
  ... truncated ...
```
