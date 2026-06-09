# SecurityLogicControl::ShowFailDlg(HWND__ *,int)

- ea: `0x18000592c`
- end: `0x180005be8`
- name: `?ShowFailDlg@SecurityLogicControl@@SAHPEAUHWND__@@H@Z`
- size: `700`
- prototype: `__int64 __fastcall(HWND, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006520`
- `0x1800072a4`
- `0x180007b08`

## callees

- `0x180001b90`
- `0x180004838`
- `0x180004c48`
- `0x180004f20`
- `0x180004fac`
- `0x180005054`
- `0x1800050b8`
- `0x1800052cc`
- `0x18000592c`
- `0x180006340`
- `0x18000a616`

## import_xrefs

- `USER32!IsWindow` at `0x180005979`
- `USER32!IsWindow` at `0x180005979`
- `USER32!FindWindowExW` at `0x180005968`
- `USER32!FindWindowExW` at `0x180005968`
- `USER32!SendMessageW` at `0x180005991`
- `USER32!SendMessageW` at `0x180005991`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall SecurityLogicControl::ShowFailDlg(HWND a1, int a2)
{
  LPARAM v2; // r15
  HWND Window; // rax
  HWND v5; // rbx
  char *v7; // rdx
  char *v8; // rbx
  int *v9; // rdi
  __int64 v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // r14d
  _BYTE *v14; // rdx
  char *v15; // rdi
  int *v16; // rsi
  __int64 v17; // rdi
  _BYTE *v18; // rdx
  int *v19; // rsi
  __int64 v20; // rbx
  ATL::CStringData *v21; // rsi
  char *v22; // rax
  BOOL v23; // edi
  char *v24[2]; // [rsp+20h] [rbp-79h] BYREF
  int v25; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v26[2]; // [rsp+34h] [rbp-65h] BYREF
  int v27; // [rsp+44h] [rbp-55h]
  int v28; // [rsp+48h] [rbp-51h]
  __int64 v29; // [rsp+4Ch] [rbp-4Dh]
  __int64 v30; // [rsp+54h] [rbp-45h]
  char *v31; // [rsp+5Ch] [rbp-3Dh]
  char *v32; // [rsp+64h] [rbp-35h]
  int v33; // [rsp+6Ch] [rbp-2Dh]
  __int64 v34; // [rsp+70h] [rbp-29h]
  __int64 (__fastcall *v35)(HWND, int, __int64, __int64); // [rsp+BCh] [rbp+23h]
  __int64 v36; // [rsp+C4h] [rbp+2Bh]
  char *v37; // [rsp+110h] [rbp+77h] BYREF
  char *v38; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = a2;
  if ( !g_hMainWnd && (Window = FindWindowExW(0, 0, L"wscui_class", 0), (v5 = Window) != 0) && IsWindow(Window) )
  {
    SendMessageW(v5, 0x44Cu, 0, v2);
    return 1;
  }
  else
  {
    v25 = 160;
    memset_0(v26, 0, 0x9Cu);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v37);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v38);
    v7 = *SecurityLogicControl::GetString(v24, v2, 0);
    v8 = v37;
    v9 = (int *)(v37 - 24);
    if ( v7 - 24 != v37 - 24 )
    {
      if ( v9[4] >= 0 && *((_QWORD *)v7 - 3) == *(_QWORD *)v9 )
      {
        v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v9);
        v8 = (char *)(v10 + 24);
        v37 = v8;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v37, v7, *((_DWORD *)v7 - 4));
        v8 = v37;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v24[0] - 24));
    v11 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
            &v37,
            L"<A");
    v13 = v11;
    if ( v11 == -1 )
    {
      v15 = v38;
    }
    else
    {
      v14 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                         &v37,
                         v24,
                         *((_DWORD *)v8 - 4) - v11);
      v15 = v38;
      v16 = (int *)(v38 - 24);
      if ( v14 - 24 != v38 - 24 )
      {
        if ( v16[4] >= 0 && *((_QWORD *)v14 - 3) == *(_QWORD *)v16 )
        {
          v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v16);
          v15 = (char *)(v17 + 24);
          v38 = v15;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v38, v14, *((_DWORD *)v14 - 4));
          v15 = v38;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v24[0] - 24));
      v18 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                         &v37,
                         v24,
                         v13);
      v19 = (int *)(v8 - 24);
      if ( v18 - 24 != v8 - 24 )
      {
        if ( v19[4] >= 0 && *((_QWORD *)v18 - 3) == *(_QWORD *)v19 )
        {
          v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v19);
          v8 = (char *)(v20 + 24);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v37, v18, *((_DWORD *)v18 - 4));
          v8 = v37;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v24[0] - 24));
    }
    v26[1] = hInstance;
    v26[0] = a1;
    v29 = 1181;
    v31 = v8;
    v21 = (ATL::CStringData *)(v15 - 24);
    v22 = 0;
    if ( *((int *)v15 - 4) > 0 )
      v22 = v15;
    v32 = v22;
    v30 = ((_DWORD)v2 != 1164) + 65533LL;
    v33 = 0;
    v34 = 0;
    v28 = 32;
    v27 = 9;
    v36 = 0;
    v35 = ShowFailDialogCallbackProc;
    v23 = (int)IsolationAwareTaskDialogIndirect((__int64)&v25, 0, v12, 0) >= 0;
    ATL::CStringData::Release(v21);
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
    return v23;
  }
}

```

## disassembly

```asm
0x18000592c  mov     [rsp-8+arg_0], rbx
0x180005931  mov     [rsp-8+arg_8], rsi
0x180005936  push    rbp
0x180005937  push    rdi
0x180005938  push    r12
0x18000593a  push    r14
0x18000593c  push    r15
0x18000593e  lea     rbp, [rsp-37h]
0x180005943  sub     rsp, 0D0h
0x18000594a  movsxd  r15, edx
0x18000594d  mov     r12, rcx
0x180005950  cmp     cs:?g_hMainWnd@@3PEAUHWND__@@EA, 0; HWND__ * g_hMainWnd
0x180005958  jnz     short loc_1800059A1
0x18000595a  xor     r9d, r9d; lpszWindow
0x18000595d  lea     r8, szClass; "wscui_class"
0x180005964  xor     edx, edx; hWndChildAfter
0x180005966  xor     ecx, ecx; hWndParent
0x180005968  call    cs:__imp_FindWindowExW
0x18000596e  mov     rbx, rax
0x180005971  test    rax, rax
0x180005974  jz      short loc_1800059A1
0x180005976  mov     rcx, rax; hWnd
0x180005979  call    cs:__imp_IsWindow
0x18000597f  test    eax, eax
0x180005981  jz      short loc_1800059A1
0x180005983  mov     r9, r15; lParam
0x180005986  xor     r8d, r8d; wParam
0x180005989  mov     edx, 44Ch; Msg
0x18000598e  mov     rcx, rbx; hWnd
0x180005991  call    cs:__imp_SendMessageW
0x180005997  mov     eax, 1
0x18000599c  jmp     loc_180005BCC
0x1800059a1  mov     [rbp+57h+var_C0], 0A0h
0x1800059a8  xor     edx, edx; Val
0x1800059aa  mov     r8d, 9Ch; Size
0x1800059b0  lea     rcx, [rbp+57h+var_BC]; void *
0x1800059b4  call    memset_0
0x1800059b9  lea     rcx, [rbp+57h+arg_10]
0x1800059bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800059c2  nop
0x1800059c3  lea     rcx, [rbp+57h+arg_18]
0x1800059c7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800059cc  nop
0x1800059cd  xor     r8d, r8d
0x1800059d0  mov     edx, r15d
0x1800059d3  lea     rcx, [rbp+57h+var_D0]
0x1800059d7  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x1800059dc  nop
0x1800059dd  mov     rdx, [rax]
0x1800059e0  lea     rcx, [rdx-18h]
0x1800059e4  mov     rbx, [rbp+57h+arg_10]
0x1800059e8  lea     rdi, [rbx-18h]
0x1800059ec  cmp     rcx, rdi
0x1800059ef  jz      short loc_180005A2A
0x1800059f1  cmp     dword ptr [rdi+10h], 0
0x1800059f5  jl      short loc_180005A19
0x1800059f7  mov     rax, [rdi]
0x1800059fa  cmp     [rcx], rax
0x1800059fd  jnz     short loc_180005A19
0x1800059ff  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005a04  mov     rbx, rax
0x180005a07  mov     rcx, rdi; this
0x180005a0a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005a0f  add     rbx, 18h
0x180005a13  mov     [rbp+57h+arg_10], rbx
0x180005a17  jmp     short loc_180005A2A
0x180005a19  mov     r8d, [rdx-10h]
0x180005a1d  lea     rcx, [rbp+57h+arg_10]
0x180005a21  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180005a26  mov     rbx, [rbp+57h+arg_10]
0x180005a2a  mov     rcx, [rbp+57h+var_D0]
0x180005a2e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005a32  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005a37  lea     rdx, aA; "<A"
0x180005a3e  lea     rcx, [rbp+57h+arg_10]
0x180005a42  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180005a47  mov     r14d, eax
0x180005a4a  cmp     eax, 0FFFFFFFFh
0x180005a4d  jz      loc_180005B27
0x180005a53  mov     r8d, [rbx-10h]
0x180005a57  sub     r8d, eax
0x180005a5a  lea     rdx, [rbp+57h+var_D0]
0x180005a5e  lea     rcx, [rbp+57h+arg_10]
0x180005a62  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x180005a67  nop
0x180005a68  mov     rdx, [rax]
0x180005a6b  lea     rcx, [rdx-18h]
0x180005a6f  mov     rdi, [rbp+57h+arg_18]
0x180005a73  lea     rsi, [rdi-18h]
0x180005a77  cmp     rcx, rsi
0x180005a7a  jz      short loc_180005AB5
0x180005a7c  cmp     dword ptr [rsi+10h], 0
0x180005a80  jl      short loc_180005AA4
0x180005a82  mov     rax, [rsi]
0x180005a85  cmp     [rcx], rax
0x180005a88  jnz     short loc_180005AA4
0x180005a8a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005a8f  mov     rdi, rax
0x180005a92  mov     rcx, rsi; this
0x180005a95  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005a9a  add     rdi, 18h
0x180005a9e  mov     [rbp+57h+arg_18], rdi
0x180005aa2  jmp     short loc_180005AB5
0x180005aa4  mov     r8d, [rdx-10h]
0x180005aa8  lea     rcx, [rbp+57h+arg_18]
0x180005aac  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180005ab1  mov     rdi, [rbp+57h+arg_18]
0x180005ab5  mov     rcx, [rbp+57h+var_D0]
0x180005ab9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005abd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005ac2  mov     r8d, r14d
0x180005ac5  lea     rdx, [rbp+57h+var_D0]
0x180005ac9  lea     rcx, [rbp+57h+arg_10]
0x180005acd  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180005ad2  nop
0x180005ad3  mov     rdx, [rax]
0x180005ad6  lea     rcx, [rdx-18h]
0x180005ada  lea     rsi, [rbx-18h]
0x180005ade  cmp     rcx, rsi
0x180005ae1  jz      short loc_180005B18
0x180005ae3  cmp     dword ptr [rsi+10h], 0
0x180005ae7  jl      short loc_180005B07
0x180005ae9  mov     rax, [rsi]
0x180005aec  cmp     [rcx], rax
0x180005aef  jnz     short loc_180005B07
0x180005af1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005af6  mov     rbx, rax
0x180005af9  mov     rcx, rsi; this
0x180005afc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005b01  add     rbx, 18h
0x180005b05  jmp     short loc_180005B18
0x180005b07  mov     r8d, [rdx-10h]
0x180005b0b  lea     rcx, [rbp+57h+arg_10]
0x180005b0f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180005b14  mov     rbx, [rbp+57h+arg_10]
0x180005b18  mov     rcx, [rbp+57h+var_D0]
0x180005b1c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005b20  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005b25  jmp     short loc_180005B2B
0x180005b27  mov     rdi, [rbp+57h+arg_18]
0x180005b2b  mov     rax, cs:hInstance
0x180005b32  mov     [rbp+57h+var_B4], rax
0x180005b36  mov     [rbp+57h+var_BC], r12
0x180005b3a  mov     [rbp+57h+var_A4], 49Dh
0x180005b42  mov     [rbp+57h+var_94], rbx
0x180005b46  lea     rsi, [rdi-18h]
0x180005b4a  xor     eax, eax
0x180005b4c  cmp     [rsi+8], eax
0x180005b4f  cmovg   rax, rdi
0x180005b53  mov     [rbp+57h+var_8C], rax
0x180005b57  xor     eax, eax
0x180005b59  cmp     r15d, 48Ch
0x180005b60  setnz   al
0x180005b63  add     rax, 0FFFDh
0x180005b69  mov     [rbp+57h+var_9C], rax
0x180005b6d  mov     [rbp+57h+var_84], 0
0x180005b74  mov     [rbp+57h+var_80], 0
0x180005b7c  mov     [rbp+57h+var_A8], 20h ; ' '
0x180005b83  mov     [rbp+57h+var_AC], 9
0x180005b8a  mov     [rbp+57h+var_2C], 0
0x180005b92  lea     rax, ?ShowFailDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; ShowFailDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180005b99  mov     [rbp+57h+var_34], rax
0x180005b9d  xor     r9d, r9d
0x180005ba0  xor     edx, edx
0x180005ba2  lea     rcx, [rbp+57h+var_C0]
0x180005ba6  call    IsolationAwareTaskDialogIndirect
0x180005bab  test    eax, eax
0x180005bad  js      short loc_180005BB6
0x180005baf  mov     edi, 1
0x180005bb4  jmp     short loc_180005BB8
0x180005bb6  xor     edi, edi
0x180005bb8  mov     rcx, rsi; this
0x180005bbb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005bc0  nop
0x180005bc1  lea     rcx, [rbx-18h]; this
0x180005bc5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005bca  mov     eax, edi
0x180005bcc  lea     r11, [rsp+0F0h+var_20]
0x180005bd4  mov     rbx, [r11+30h]
0x180005bd8  mov     rsi, [r11+38h]
0x180005bdc  mov     rsp, r11
0x180005bdf  pop     r15
0x180005be1  pop     r14
0x180005be3  pop     r12
0x180005be5  pop     rdi
0x180005be6  pop     rbp
0x180005be7  retn
```
