# WdcDataCollectorNode::UpdateAlertsPage(HWND__ *,ulong,ulong,ulong,ulong)

- ea: `0x1800654a0`
- end: `0x18006573d`
- name: `?UpdateAlertsPage@WdcDataCollectorNode@@CAJPEAUHWND__@@KKKK@Z`
- size: `669`
- prototype: `__int64 __usercall@<rax>(HWND hDlg@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18005ca10`
- `0x18005dd4c`
- `0x18005e530`
- `0x180064020`
- `0x1800644c0`
- `0x1800647c0`

## callees

- `0x18000b854`
- `0x18002ac84`
- `0x18003b0ac`
- `0x1800654a0`

## import_xrefs

- `USER32!EnableWindow` at `0x18006557f`
- `USER32!EnableWindow` at `0x18006558a`
- `USER32!EnableWindow` at `0x18006557f`
- `USER32!EnableWindow` at `0x18006558a`
- `USER32!SetWindowTextW` at `0x18006567b`
- `USER32!SetWindowTextW` at `0x18006567b`
- `USER32!SendMessageW` at `0x180065526`
- `USER32!SendMessageW` at `0x180065548`
- `USER32!SendMessageW` at `0x1800655c3`
- `USER32!SendMessageW` at `0x18006561c`
- `USER32!SendMessageW` at `0x18006564a`
- `USER32!SendMessageW` at `0x1800656c1`
- `USER32!SendMessageW` at `0x180065526`
- `USER32!SendMessageW` at `0x180065548`
- `USER32!SendMessageW` at `0x1800655c3`
- `USER32!SendMessageW` at `0x18006561c`
- `USER32!SendMessageW` at `0x18006564a`
- `USER32!SendMessageW` at `0x1800656c1`
- `USER32!GetDlgItem` at `0x1800654fc`
- `USER32!GetDlgItem` at `0x18006550f`
- `USER32!GetDlgItem` at `0x180065574`
- `USER32!GetDlgItem` at `0x180065607`
- `USER32!GetDlgItem` at `0x180065636`
- `USER32!GetDlgItem` at `0x1800656ad`
- `USER32!GetDlgItem` at `0x1800654fc`
- `USER32!GetDlgItem` at `0x18006550f`
- `USER32!GetDlgItem` at `0x180065574`
- `USER32!GetDlgItem` at `0x180065607`
- `USER32!GetDlgItem` at `0x180065636`
- `USER32!GetDlgItem` at `0x1800656ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800654f1`
- `OLEAUT32!__imp_VariantInit` at `0x1800654f1`
- `OLEAUT32!__imp_VariantClear` at `0x180065721`
- `OLEAUT32!__imp_VariantClear` at `0x180065721`
- `OLEAUT32!__imp_VariantCopy` at `0x1800655e8`
- `OLEAUT32!__imp_VariantCopy` at `0x1800656ef`
- `OLEAUT32!__imp_VariantCopy` at `0x1800655e8`
- `OLEAUT32!__imp_VariantCopy` at `0x1800656ef`
- `OLEAUT32!__imp_VariantChangeType` at `0x180065664`
- `OLEAUT32!__imp_VariantChangeType` at `0x180065664`

## string_xrefs

- `0x180065709`: `WdcDataCollectorNode::UpdateAlertsPage`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorNode::UpdateAlertsPage(HWND hDlg, int a2, int a3, int a4, int nIDDlgItem)
{
  unsigned int v8; // ebx
  int v10; // r14d
  HWND DlgItem; // rdi
  HWND v12; // r13
  LRESULT v13; // rax
  int i; // edi
  bool v15; // zf
  BOOL v16; // edi
  HWND v17; // rax
  VARIANTARG *v18; // rdi
  HRESULT Value; // eax
  HWND v20; // rax
  HWND v21; // rax
  HWND v22; // rax
  int v23; // eax
  double dblVal; // xmm0_8
  VARIANTARG pvarg; // [rsp+30h] [rbp-81h] BYREF
  LRESULT v27; // [rsp+48h] [rbp-69h]
  HWND hWnd; // [rsp+50h] [rbp-61h]
  LPARAM lParam; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v30[32]; // [rsp+68h] [rbp-49h] BYREF
  VARIANTARG *pvargSrc; // [rsp+88h] [rbp-29h]

  v8 = 0;
  v10 = -1;
  memset_0(&lParam, 0, 0x58u);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  DlgItem = GetDlgItem(hDlg, a3);
  hWnd = DlgItem;
  v12 = GetDlgItem(hDlg, nIDDlgItem);
  v13 = SendMessageW(DlgItem, 0x1004u, 0, 0);
  v27 = v13;
  for ( i = 0; i < (int)v13; ++i )
  {
    v15 = (SendMessageW(hWnd, 0x102Cu, i, 2) & 2) == 0;
    LODWORD(v13) = v27;
    if ( !v15 )
    {
      v10 = i;
      break;
    }
  }
  v16 = (int)v13 > 0 && v10 >= 0;
  v17 = GetDlgItem(hDlg, a4);
  EnableWindow(v17, v16);
  EnableWindow(v12, v16);
  if ( v10 >= 0 )
  {
    memset_0(v30, 0, 0x50u);
    LODWORD(lParam) = 4;
    HIDWORD(lParam) = v10;
    SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)&lParam);
    v18 = pvargSrc;
    if ( pvargSrc )
    {
      if ( a2 == a3 )
      {
        Value = VariantCopy(&pvarg, pvargSrc);
        v8 = Value;
        if ( Value >= 0 )
        {
          if ( pvarg.dblVal >= 0.0 )
          {
            v21 = GetDlgItem(hDlg, a4);
            SendMessageW(v21, 0x14Eu, 0, 0);
          }
          else
          {
            v20 = GetDlgItem(hDlg, a4);
            SendMessageW(v20, 0x14Eu, 1u, 0);
            pvarg.dblVal = pvarg.dblVal * -1.0;
          }
          Value = VariantChangeType(&pvarg, &pvarg, 4u, 8u);
          v8 = Value;
          if ( Value >= 0 )
          {
            SetWindowTextW(v12, pvarg.bstrVal);
            goto LABEL_27;
          }
        }
LABEL_26:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
          "WdcDataCollectorNode::UpdateAlertsPage",
          0,
          L"FAILURE: 0x%08x",
          Value);
        goto LABEL_27;
      }
      if ( a2 == nIDDlgItem || a2 == a4 )
      {
        Value = WdcNumericEditorGetValue(v12, &pvarg);
        v8 = Value;
        if ( Value < 0 )
          goto LABEL_26;
        v22 = GetDlgItem(hDlg, a4);
        v23 = SendMessageW(v22, 0x147u, 0, 0);
        dblVal = pvarg.dblVal;
        if ( v23 == 1 )
        {
          dblVal = pvarg.dblVal * -1.0;
          pvarg.dblVal = pvarg.dblVal * -1.0;
        }
        if ( dblVal != v18->dblVal )
        {
          Value = VariantCopy(v18, &pvarg);
          v8 = Value;
          if ( Value < 0 )
            goto LABEL_26;
        }
      }
    }
  }
LABEL_27:
  VariantClear(&pvarg);
  return v8;
}

```

## disassembly

```asm
0x1800654a0  mov     [rsp-8+arg_10], r8d
0x1800654a5  push    rbp
0x1800654a6  push    rbx
0x1800654a7  push    rsi
0x1800654a8  push    rdi
0x1800654a9  push    r12
0x1800654ab  push    r13
0x1800654ad  push    r14
0x1800654af  push    r15
0x1800654b1  lea     rbp, [rsp-17h]
0x1800654b6  sub     rsp, 0C8h
0x1800654bd  mov     edi, r8d
0x1800654c0  mov     r12d, edx
0x1800654c3  mov     r15, rcx
0x1800654c6  xor     ebx, ebx
0x1800654c8  xor     edx, edx; Val
0x1800654ca  lea     rcx, [rbp+4Fh+lParam]; void *
0x1800654ce  mov     esi, r9d
0x1800654d1  or      r14d, 0FFFFFFFFh
0x1800654d5  lea     r8d, [rbx+58h]; Size
0x1800654d9  call    memset_0
0x1800654de  xorps   xmm0, xmm0
0x1800654e1  lea     rcx, [rsp+100h+pvarg]; pvarg
0x1800654e6  xor     eax, eax
0x1800654e8  movups  xmmword ptr [rsp+100h+pvarg], xmm0
0x1800654ed  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x1800654f1  call    cs:__imp_VariantInit
0x1800654f7  mov     edx, edi; nIDDlgItem
0x1800654f9  mov     rcx, r15; hDlg
0x1800654fc  call    cs:__imp_GetDlgItem
0x180065502  mov     edx, [rbp+4Fh+nIDDlgItem]; nIDDlgItem
0x180065505  mov     rcx, r15; hDlg
0x180065508  mov     rdi, rax
0x18006550b  mov     [rbp+4Fh+hWnd], rax
0x18006550f  call    cs:__imp_GetDlgItem
0x180065515  xor     r9d, r9d; lParam
0x180065518  xor     r8d, r8d; wParam
0x18006551b  mov     edx, 1004h; Msg
0x180065520  mov     rcx, rdi; hWnd
0x180065523  mov     r13, rax
0x180065526  call    cs:__imp_SendMessageW
0x18006552c  mov     [rbp+4Fh+var_B8], rax
0x180065530  xor     edi, edi
0x180065532  cmp     edi, eax
0x180065534  jge     short loc_18006555D
0x180065536  mov     rcx, [rbp+4Fh+hWnd]; hWnd
0x18006553a  mov     edx, 102Ch; Msg
0x18006553f  movsxd  r8, edi; wParam
0x180065542  mov     r9d, 2; lParam
0x180065548  call    cs:__imp_SendMessageW
0x18006554e  test    al, 2
0x180065550  mov     rax, [rbp+4Fh+var_B8]
0x180065554  jnz     short loc_18006555A
0x180065556  inc     edi
0x180065558  jmp     short loc_180065532
0x18006555a  mov     r14d, edi
0x18006555d  test    eax, eax
0x18006555f  jle     short loc_18006556D
0x180065561  test    r14d, r14d
0x180065564  js      short loc_18006556D
0x180065566  mov     edi, 1
0x18006556b  jmp     short loc_18006556F
0x18006556d  xor     edi, edi
0x18006556f  mov     edx, esi; nIDDlgItem
0x180065571  mov     rcx, r15; hDlg
0x180065574  call    cs:__imp_GetDlgItem
0x18006557a  mov     rcx, rax; hWnd
0x18006557d  mov     edx, edi; bEnable
0x18006557f  call    cs:__imp_EnableWindow
0x180065585  mov     edx, edi; bEnable
0x180065587  mov     rcx, r13; hWnd
0x18006558a  call    cs:__imp_EnableWindow
0x180065590  test    r14d, r14d
0x180065593  js      loc_18006571C
0x180065599  xor     edx, edx; Val
0x18006559b  lea     rcx, [rbp+4Fh+var_98]; void *
0x18006559f  lea     r8d, [rdx+50h]; Size
0x1800655a3  call    memset_0
0x1800655a8  mov     rcx, [rbp+4Fh+hWnd]; hWnd
0x1800655ac  lea     r9, [rbp+4Fh+lParam]; lParam
0x1800655b0  xor     r8d, r8d; wParam
0x1800655b3  mov     dword ptr [rbp+4Fh+lParam], 4
0x1800655ba  mov     edx, 104Bh; Msg
0x1800655bf  mov     dword ptr [rbp+4Fh+lParam+4], r14d
0x1800655c3  call    cs:__imp_SendMessageW
0x1800655c9  mov     rdi, [rbp+4Fh+pvargSrc]
0x1800655cd  test    rdi, rdi
0x1800655d0  jz      loc_18006571C
0x1800655d6  cmp     r12d, [rbp+4Fh+arg_10]
0x1800655da  jnz     loc_180065686
0x1800655e0  mov     rdx, rdi; pvargSrc
0x1800655e3  lea     rcx, [rsp+100h+pvarg]; pvargDest
0x1800655e8  call    cs:__imp_VariantCopy
0x1800655ee  mov     ebx, eax
0x1800655f0  test    eax, eax
0x1800655f2  js      loc_1800656FB
0x1800655f8  xorps   xmm0, xmm0
0x1800655fb  mov     edx, esi; nIDDlgItem
0x1800655fd  comisd  xmm0, qword ptr [rbp+4Fh+pvarg+8]
0x180065602  mov     rcx, r15; hDlg
0x180065605  jbe     short loc_180065636
0x180065607  call    cs:__imp_GetDlgItem
0x18006560d  xor     r9d, r9d; lParam
0x180065610  mov     edx, 14Eh; Msg
0x180065615  mov     rcx, rax; hWnd
0x180065618  lea     r8d, [r9+1]; wParam
0x18006561c  call    cs:__imp_SendMessageW
0x180065622  movsd   xmm0, qword ptr [rbp+4Fh+pvarg+8]
0x180065627  mulsd   xmm0, cs:__real@bff0000000000000
0x18006562f  movsd   qword ptr [rbp+4Fh+pvarg+8], xmm0
0x180065634  jmp     short loc_180065650
0x180065636  call    cs:__imp_GetDlgItem
0x18006563c  xor     r9d, r9d; lParam
0x18006563f  xor     r8d, r8d; wParam
0x180065642  mov     rcx, rax; hWnd
0x180065645  mov     edx, 14Eh; Msg
0x18006564a  call    cs:__imp_SendMessageW
0x180065650  mov     r9d, 8; vt
0x180065656  lea     rdx, [rsp+100h+pvarg]; pvarSrc
0x18006565b  lea     rcx, [rsp+100h+pvarg]; pvargDest
0x180065660  lea     r8d, [r9-4]; wFlags
0x180065664  call    cs:__imp_VariantChangeType
0x18006566a  mov     ebx, eax
0x18006566c  test    eax, eax
0x18006566e  js      loc_1800656FB
0x180065674  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]; lpString
0x180065678  mov     rcx, r13; hWnd
0x18006567b  call    cs:__imp_SetWindowTextW
0x180065681  jmp     loc_18006571C
0x180065686  cmp     r12d, [rbp+4Fh+nIDDlgItem]
0x18006568a  jz      short loc_180065695
0x18006568c  cmp     r12d, esi
0x18006568f  jnz     loc_18006571C
0x180065695  lea     rdx, [rsp+100h+pvarg]; pvarSrc
0x18006569a  mov     rcx, r13; hWnd
0x18006569d  call    ?WdcNumericEditorGetValue@@YAJPEAUHWND__@@PEAUtagVARIANT@@@Z; WdcNumericEditorGetValue(HWND__ *,tagVARIANT *)
0x1800656a2  mov     ebx, eax
0x1800656a4  test    eax, eax
0x1800656a6  js      short loc_1800656FB
0x1800656a8  mov     edx, esi; nIDDlgItem
0x1800656aa  mov     rcx, r15; hDlg
0x1800656ad  call    cs:__imp_GetDlgItem
0x1800656b3  xor     r9d, r9d; lParam
0x1800656b6  xor     r8d, r8d; wParam
0x1800656b9  mov     rcx, rax; hWnd
0x1800656bc  mov     edx, 147h; Msg
0x1800656c1  call    cs:__imp_SendMessageW
0x1800656c7  movsd   xmm0, qword ptr [rbp+4Fh+pvarg+8]
0x1800656cc  cmp     eax, 1
0x1800656cf  jnz     short loc_1800656DE
0x1800656d1  mulsd   xmm0, cs:__real@bff0000000000000
0x1800656d9  movsd   qword ptr [rbp+4Fh+pvarg+8], xmm0
0x1800656de  ucomisd xmm0, qword ptr [rdi+8]
0x1800656e3  jp      short loc_1800656E7
0x1800656e5  jz      short loc_18006571C
0x1800656e7  lea     rdx, [rsp+100h+pvarg]; pvargSrc
0x1800656ec  mov     rcx, rdi; pvargDest
0x1800656ef  call    cs:__imp_VariantCopy
0x1800656f5  mov     ebx, eax
0x1800656f7  test    eax, eax
0x1800656f9  jns     short loc_18006571C
0x1800656fb  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180065702  mov     [rsp+100h+var_E0], eax
0x180065706  xor     r8d, r8d; int
0x180065709  lea     rdx, aWdcdatacollect_65; "WdcDataCollectorNode::UpdateAlertsPage"
0x180065710  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180065717  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006571c  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180065721  call    cs:__imp_VariantClear
0x180065727  mov     eax, ebx
0x180065729  add     rsp, 0C8h
0x180065730  pop     r15
0x180065732  pop     r14
0x180065734  pop     r13
0x180065736  pop     r12
0x180065738  pop     rdi
0x180065739  pop     rsi
0x18006573a  pop     rbx
0x18006573b  pop     rbp
0x18006573c  retn
```
