# CIconicBitmapRegistry::LivePreviewBitmapReceived(CWindowData *,ulong,uint,uint,tagPOINT const *,void const *,unsigned __int64,ulong)

- ea: `0x1800927a0`
- end: `0x180092ade`
- name: `?LivePreviewBitmapReceived@CIconicBitmapRegistry@@QEAAJPEAVCWindowData@@KIIPEBUtagPOINT@@PEBX_KK@Z`
- size: `830`
- prototype: `__int64 __usercall@<rax>(CIconicBitmapRegistry *__hidden this@<rcx>, struct CWindowData *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const struct tagPOINT *, const void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800df208`

## callees

- `0x18001a690`
- `0x18001ce00`
- `0x18001f43c`
- `0x18003ffa0`
- `0x1800402d8`
- `0x18004067c`
- `0x180078ae4`
- `0x180089e80`
- `0x1800927a0`
- `0x1800da0ec`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180092818`
- `USER32!GetWindowThreadProcessId` at `0x180092818`

## pseudocode

```c
__int64 __fastcall CIconicBitmapRegistry::LivePreviewBitmapReceived(
        unsigned __int64 this,
        struct CWindowData *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        const struct tagPOINT *a6,
        void *a7,
        unsigned __int64 a8,
        char a9)
{
  CBaseObject *v9; // r15
  bool v11; // zf
  CIconicBitmapRegistry *v14; // rsi
  unsigned __int64 v15; // rax
  struct CWindowData *MDIOwner; // rbx
  int WindowRestoreRect; // eax
  unsigned int v18; // edi
  unsigned int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // rcx
  _DWORD *v22; // rcx
  unsigned int v23; // r9d
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  const struct tagPOINT *v29; // rax
  char v30; // bl
  char v31; // r8
  __int64 v32; // rcx
  CBaseObject *v34; // [rsp+30h] [rbp-20h] BYREF
  struct tagRECT v35; // [rsp+38h] [rbp-18h] BYREF
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF

  v9 = 0;
  v11 = (*((_BYTE *)a2 + 738) & 2) == 0;
  v34 = 0;
  v14 = (CIconicBitmapRegistry *)this;
  dwProcessId = 0;
  if ( v11
    || (this = a5 * (unsigned __int64)a4, this > 0xFFFFFFFF)
    || (v15 = 4LL * (unsigned int)this, v15 > 0xFFFFFFFF)
    || a8 < (unsigned int)v15
    || !GetWindowThreadProcessId(*((HWND *)a2 + 5), &dwProcessId)
    || a3 != dwProcessId )
  {
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(this, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
    v18 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F74D0, 1u, -2147024809, 0x2D4u, 0);
    goto LABEL_48;
  }
  MDIOwner = CWindowData::GetMDIOwner(a2);
  if ( !MDIOwner )
    MDIOwner = a2;
  v35 = 0;
  WindowRestoreRect = CWindowData::GetWindowRestoreRect(MDIOwner, &v35, 0);
  v18 = WindowRestoreRect;
  if ( WindowRestoreRect < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F74D0, 1u, WindowRestoreRect, 0x2DFu, 0);
    return v18;
  }
  v19 = 0;
  v20 = 0;
  if ( v35.right - v35.left >= 0 )
    v19 = v35.right - v35.left;
  if ( v35.bottom - v35.top >= 0 )
    v20 = v35.bottom - v35.top;
  v21 = *((_QWORD *)MDIOwner + 60);
  if ( v21 )
  {
    v22 = *(_DWORD **)(v21 + 32);
    v23 = 0;
    if ( v22[14] - v22[12] >= 0 )
      v23 = v22[14] - v22[12];
    if ( v19 > v23 )
      v23 = v19;
    v24 = v22[15] - v22[13];
    v25 = 0;
    if ( v24 >= 0 )
      v25 = (unsigned int)v24;
    if ( v20 > (unsigned int)v25 )
      v25 = v20;
  }
  else
  {
    v23 = v19;
    v25 = v20;
  }
  if ( a4 > v23 || a5 > (unsigned int)v25 )
  {
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(v25, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
    v18 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F74D0, 1u, -2147024809, 0x2EAu, 0);
  }
  else
  {
    v26 = *((_QWORD *)v14 + 12);
    if ( v26 && *(struct CWindowData **)(v26 + 72) == a2 )
    {
      v27 = CBitmapSource::Create(a4, a5, a4, a5, a7, &v34);
      v18 = v27;
      if ( v27 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F74D0, 1u, v27, 0x2F6u, 0);
        v9 = v34;
      }
      else
      {
        if ( *((_BYTE *)v14 + 89) )
        {
          v28 = CIconicBitmapRegistry::RequestBitmap(v14, (struct CWindowData *)0xFFFFFFFFFFFFFFFFLL, 0);
          v18 = v28;
          if ( v28 < 0 )
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F74D0, 1u, v28, 0x2FBu, 0);
        }
        v29 = a6;
        v30 = *((_BYTE *)v14 + 88);
        v31 = a9;
        *(_WORD *)((char *)v14 + 89) = 0;
        v9 = v34;
        *((_BYTE *)v14 + 88) = 1;
        *((struct tagPOINT *)v14 + 13) = *v29;
        CWindowIconic::SetBitmap(*((CWindowIconic **)v14 + 12), v9, v31 & 1, 1);
        if ( !v30 )
          CWindowIconic::OnRepresentationTypeUpdated(*((CWindowIconic **)v14 + 12));
        if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
          McTemplateU0qp_EtwEventWriteTransfer(v32, UdwmManageIconicThumbnail_Info, 0, *((_QWORD *)a2 + 5));
      }
LABEL_48:
      if ( v9 )
        CBaseObject::Release(v9);
      return v18;
    }
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(v25, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
  }
  return v18;
}

```

## disassembly

```asm
0x1800927a0  mov     [rsp-28h+arg_0], rbx
0x1800927a5  mov     [rsp-28h+arg_10], rsi
0x1800927aa  push    rbp
0x1800927ab  push    rdi
0x1800927ac  push    r12
0x1800927ae  push    r14
0x1800927b0  push    r15
0x1800927b2  mov     rbp, rsp
0x1800927b5  sub     rsp, 50h
0x1800927b9  xor     r15d, r15d
0x1800927bc  mov     r12d, r9d
0x1800927bf  test    byte ptr [rdx+2E2h], 2
0x1800927c6  mov     ebx, r8d
0x1800927c9  mov     r14, rdx
0x1800927cc  mov     [rbp+var_20], r15
0x1800927d0  mov     rsi, rcx
0x1800927d3  mov     [rbp+dwProcessId], r15d
0x1800927d7  jz      loc_180092A6B
0x1800927dd  mov     eax, [rbp+arg_20]
0x1800927e0  mov     ecx, r12d
0x1800927e3  imul    rcx, rax
0x1800927e7  mov     edx, 0FFFFFFFFh
0x1800927ec  cmp     rcx, rdx
0x1800927ef  ja      loc_180092A6B
0x1800927f5  mov     eax, ecx
0x1800927f7  shl     rax, 2
0x1800927fb  cmp     rax, rdx
0x1800927fe  ja      loc_180092A6B
0x180092804  mov     eax, eax
0x180092806  cmp     [rbp+arg_38], rax
0x18009280a  jb      loc_180092A6B
0x180092810  mov     rcx, [r14+28h]; hWnd
0x180092814  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180092818  call    cs:__imp_GetWindowThreadProcessId
0x18009281e  test    eax, eax
0x180092820  jz      loc_180092A6B
0x180092826  cmp     ebx, [rbp+dwProcessId]
0x180092829  jnz     loc_180092A6B
0x18009282f  mov     rcx, r14; this
0x180092832  call    ?GetMDIOwner@CWindowData@@QEAAPEAV1@XZ; CWindowData::GetMDIOwner(void)
0x180092837  test    rax, rax
0x18009283a  lea     rdx, [rbp+var_18]; struct tagRECT *
0x18009283e  mov     rbx, rax
0x180092841  xorps   xmm0, xmm0
0x180092844  cmovz   rbx, r14
0x180092848  xor     r8d, r8d; bool
0x18009284b  mov     rcx, rbx; this
0x18009284e  movups  xmmword ptr [rbp+var_18.left], xmm0
0x180092852  call    ?GetWindowRestoreRect@CWindowData@@QEAAJPEAUtagRECT@@_N@Z; CWindowData::GetWindowRestoreRect(tagRECT *,bool)
0x180092857  mov     edi, eax
0x180092859  test    eax, eax
0x18009285b  js      loc_180092A59
0x180092861  mov     ecx, [rbp+var_18.right]
0x180092864  mov     edx, r15d
0x180092867  sub     ecx, [rbp+var_18.left]
0x18009286a  mov     r8d, r15d
0x18009286d  cmovns  edx, ecx
0x180092870  mov     ecx, [rbp+var_18.bottom]
0x180092873  sub     ecx, [rbp+var_18.top]
0x180092876  cmovns  r8d, ecx
0x18009287a  mov     rcx, [rbx+1E0h]
0x180092881  test    rcx, rcx
0x180092884  jz      short loc_1800928B3
0x180092886  mov     rcx, [rcx+20h]
0x18009288a  mov     r9d, r15d
0x18009288d  mov     eax, [rcx+38h]
0x180092890  sub     eax, [rcx+30h]
0x180092893  cmovns  r9d, eax
0x180092897  mov     eax, [rcx+3Ch]
0x18009289a  cmp     edx, r9d
0x18009289d  cmova   r9d, edx
0x1800928a1  sub     eax, [rcx+34h]
0x1800928a4  mov     ecx, r15d
0x1800928a7  cmovns  ecx, eax
0x1800928aa  cmp     r8d, ecx
0x1800928ad  cmova   ecx, r8d
0x1800928b1  jmp     short loc_1800928B9
0x1800928b3  mov     r9d, edx
0x1800928b6  mov     ecx, r8d
0x1800928b9  cmp     r12d, r9d
0x1800928bc  ja      loc_180092A0C
0x1800928c2  cmp     [rbp+arg_20], ecx
0x1800928c5  ja      loc_180092A0C
0x1800928cb  mov     rax, [rsi+60h]
0x1800928cf  test    rax, rax
0x1800928d2  jz      loc_1800929E4
0x1800928d8  cmp     [rax+48h], r14
0x1800928dc  jnz     loc_1800929E4
0x1800928e2  mov     r9d, [rbp+arg_20]; unsigned int
0x1800928e6  lea     rax, [rbp+var_20]
0x1800928ea  mov     [rsp+50h+var_28], rax; struct CBitmapSource **
0x1800928ef  mov     r8d, r12d; unsigned int
0x1800928f2  mov     rax, [rbp+arg_30]
0x1800928f6  mov     edx, r9d; unsigned int
0x1800928f9  mov     ecx, r12d; unsigned int
0x1800928fc  mov     [rsp+50h+var_30], rax; void *
0x180092901  call    ?Create@CBitmapSource@@SAJIIIIPEBXPEAPEAV1@@Z; CBitmapSource::Create(uint,uint,uint,uint,void const *,CBitmapSource * *)
0x180092906  mov     edi, eax
0x180092908  test    eax, eax
0x18009290a  js      loc_1800929B5
0x180092910  cmp     [rsi+59h], r15b
0x180092914  jz      short loc_180092951
0x180092916  xor     r8d, r8d; bool
0x180092919  or      rdx, 0FFFFFFFFFFFFFFFFh; struct CWindowData *
0x18009291d  mov     rcx, rsi; this
0x180092920  call    ?RequestBitmap@CIconicBitmapRegistry@@AEAAJPEAVCWindowData@@_N@Z; CIconicBitmapRegistry::RequestBitmap(CWindowData *,bool)
0x180092925  mov     edi, eax
0x180092927  test    eax, eax
0x180092929  jns     short loc_180092951
0x18009292b  mov     r8d, 1; unsigned int
0x180092931  mov     [rsp+50h+var_28], r15; void *
0x180092936  mov     r9d, eax; int
0x180092939  mov     dword ptr [rsp+50h+var_30], 2FBh; unsigned int
0x180092941  lea     rdx, qword_1800F74D0; int *
0x180092948  lea     ecx, [r8+13h]; unsigned int
0x18009294c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180092951  mov     rax, [rbp+arg_28]
0x180092955  mov     r9b, 1; bool
0x180092958  mov     bl, [rsi+58h]
0x18009295b  mov     r8b, byte ptr [rbp+arg_40]
0x18009295f  mov     [rsi+59h], r15w
0x180092964  and     r8b, 1; bool
0x180092968  mov     r15, [rbp+var_20]
0x18009296c  mov     byte ptr [rsi+58h], 1
0x180092970  mov     rdx, r15; struct CBitmapSource *
0x180092973  mov     rcx, [rax]
0x180092976  mov     [rsi+68h], rcx
0x18009297a  mov     rcx, [rsi+60h]; this
0x18009297e  call    ?SetBitmap@CWindowIconic@@QEAAJPEAVCBitmapSource@@_N1@Z; CWindowIconic::SetBitmap(CBitmapSource *,bool,bool)
0x180092983  test    bl, bl
0x180092985  jnz     short loc_180092990
0x180092987  mov     rcx, [rsi+60h]; this
0x18009298b  call    ?OnRepresentationTypeUpdated@CWindowIconic@@QEAAJXZ; CWindowIconic::OnRepresentationTypeUpdated(void)
0x180092990  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x180092997  jz      loc_180092AB6
0x18009299d  mov     r9, [r14+28h]
0x1800929a1  lea     rdx, UdwmManageIconicThumbnail_Info
0x1800929a8  xor     r8d, r8d
0x1800929ab  call    McTemplateU0qp_EtwEventWriteTransfer
0x1800929b0  jmp     loc_180092AB6
0x1800929b5  mov     r8d, 1; unsigned int
0x1800929bb  mov     [rsp+50h+var_28], r15; void *
0x1800929c0  mov     r9d, eax; int
0x1800929c3  mov     dword ptr [rsp+50h+var_30], 2F6h; unsigned int
0x1800929cb  lea     rdx, qword_1800F74D0; int *
0x1800929d2  lea     ecx, [r8+13h]; unsigned int
0x1800929d6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800929db  mov     r15, [rbp+var_20]
0x1800929df  jmp     loc_180092AB6
0x1800929e4  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x1800929eb  jz      loc_180092AC3
0x1800929f1  mov     r9, [r14+28h]
0x1800929f5  lea     rdx, UdwmManageIconicThumbnail_Info
0x1800929fc  mov     r8d, 1
0x180092a02  call    McTemplateU0qp_EtwEventWriteTransfer
0x180092a07  jmp     loc_180092AC3
0x180092a0c  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x180092a13  jz      short loc_180092A2B
0x180092a15  mov     r9, [r14+28h]
0x180092a19  lea     rdx, UdwmManageIconicThumbnail_Info
0x180092a20  mov     r8d, 1
0x180092a26  call    McTemplateU0qp_EtwEventWriteTransfer
0x180092a2b  mov     r9d, 80070057h; int
0x180092a31  mov     [rsp+50h+var_28], r15; void *
0x180092a36  mov     edi, r9d
0x180092a39  mov     dword ptr [rsp+50h+var_30], 2EAh; unsigned int
0x180092a41  mov     r8d, 1; unsigned int
0x180092a47  lea     rdx, qword_1800F74D0; int *
0x180092a4e  lea     ecx, [r8+13h]; unsigned int
0x180092a52  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180092a57  jmp     short loc_180092AC3
0x180092a59  mov     [rsp+50h+var_28], r15
0x180092a5e  mov     r9d, eax
0x180092a61  mov     dword ptr [rsp+50h+var_30], 2DFh
0x180092a69  jmp     short loc_180092A41
0x180092a6b  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x180092a72  jz      short loc_180092A8A
0x180092a74  mov     r9, [r14+28h]
0x180092a78  lea     rdx, UdwmManageIconicThumbnail_Info
0x180092a7f  mov     r8d, 1
0x180092a85  call    McTemplateU0qp_EtwEventWriteTransfer
0x180092a8a  mov     r8d, 1; unsigned int
0x180092a90  mov     [rsp+50h+var_28], r15; void *
0x180092a95  mov     r9d, 80070057h; int
0x180092a9b  mov     dword ptr [rsp+50h+var_30], 2D4h; unsigned int
0x180092aa3  lea     rdx, qword_1800F74D0; int *
0x180092aaa  mov     edi, r9d
0x180092aad  lea     ecx, [r8+13h]; unsigned int
0x180092ab1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180092ab6  test    r15, r15
0x180092ab9  jz      short loc_180092AC3
0x180092abb  mov     rcx, r15; this
0x180092abe  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x180092ac3  lea     r11, [rsp+50h+var_s0]
0x180092ac8  mov     eax, edi
0x180092aca  mov     rbx, [r11+30h]
0x180092ace  mov     rsi, [r11+40h]
0x180092ad2  mov     rsp, r11
0x180092ad5  pop     r15
0x180092ad7  pop     r14
0x180092ad9  pop     r12
0x180092adb  pop     rdi
0x180092adc  pop     rbp
0x180092add  retn
```
