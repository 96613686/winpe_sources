# RoiIspControlSetHandler

- ea: `0x140007e70`
- end: `0x1400084f5`
- name: `RoiIspControlSetHandler`
- size: `1669`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004bac`
- `0x1400053fc`
- `0x140007e70`
- `0x140008640`
- `0x1400096a4`
- `0x140014254`
- `0x14001b118`
- `0x140040a30`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008284`
- `ntoskrnl!RtlCompareMemory` at `0x140008284`
- `ks!KsGetFilterFromIrp` at `0x140007ea0`
- `ks!KsGetFilterFromIrp` at `0x1400082c9`
- `ks!KsGetFilterFromIrp` at `0x140007ea0`
- `ks!KsGetFilterFromIrp` at `0x1400082c9`
- `ks!KsGenerateEvents` at `0x1400082f5`
- `ks!KsGenerateEvents` at `0x1400082f5`

## pseudocode

```c
__int64 __fastcall RoiIspControlSetHandler(PIRP Irp, __int64 a2, __int64 a3)
{
  PKSFILTER FilterFromIrp; // rax
  int v6; // r9d
  ULONG Length; // edx
  ULONG v8; // r8d
  const KSFILTER_DESCRIPTOR *Descriptor; // rdx
  _DWORD *Context; // r13
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // r13
  char v14; // r12
  char v15; // r15
  NTSTATUS v16; // ebx
  int v17; // edx
  int v18; // ecx
  int v19; // r9d
  __int64 v20; // rdx
  int v21; // r9d
  int v22; // ecx
  __int64 v23; // rbx
  __int16 v24; // r11
  __int16 v25; // r10
  __int64 v26; // r8
  unsigned __int64 v27; // r9
  __int16 v28; // ax
  unsigned __int64 v29; // rcx
  __int16 v30; // ax
  int v31; // edx
  int v32; // ecx
  int v33; // r9d
  size_t v34; // r12
  void *v35; // rdi
  size_t v36; // rcx
  PKSFILTER v37; // rax
  int Data; // [rsp+20h] [rbp-69h]
  int Dataa; // [rsp+20h] [rbp-69h]
  int Datab; // [rsp+20h] [rbp-69h]
  PVOID CallBackContext; // [rsp+30h] [rbp-59h]
  PVOID CallBackContexta; // [rsp+30h] [rbp-59h]
  PVOID CallBackContextb; // [rsp+30h] [rbp-59h]
  __int128 v45; // [rsp+50h] [rbp-39h] BYREF
  __int64 v46; // [rsp+60h] [rbp-29h]
  __int64 v47; // [rsp+68h] [rbp-21h]
  unsigned __int64 v48; // [rsp+70h] [rbp-19h]
  __int64 Source1; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 v50; // [rsp+80h] [rbp-9h] BYREF
  __int64 v51; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 v52; // [rsp+90h] [rbp+7h]
  __int64 Source2; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int16 v54; // [rsp+A0h] [rbp+17h]

  FilterFromIrp = KsGetFilterFromIrp(Irp);
  if ( !FilterFromIrp )
    goto LABEL_48;
  Length = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( !Length )
  {
    Irp->IoStatus.Information = 48;
    v16 = -2147483643;
    goto LABEL_41;
  }
  if ( Length < 0x30 )
  {
    v16 = -1073741789;
    goto LABEL_41;
  }
  if ( !a3
    || (v8 = *(_DWORD *)(a3 + 8), Length < v8)
    || (Descriptor = FilterFromIrp->Descriptor,
        Context = FilterFromIrp->Context,
        v11 = (__int64)FilterFromIrp->Descriptor->NodeDescriptors
            + Context[10] * FilterFromIrp->Descriptor->NodeDescriptorSize,
        v12 = *(_QWORD *)(v11 + 216),
        *(_DWORD *)(v12 + 92) < v8) )
  {
    v16 = -1073741811;
    goto LABEL_41;
  }
  v13 = *(_QWORD *)Context;
  v14 = *(_BYTE *)(v11 + 40);
  LOBYTE(Descriptor) = -125;
  v15 = *(_BYTE *)(*(_QWORD *)(v11 + 32) + 3LL);
  LOBYTE(v6) = v15;
  v46 = *(_QWORD *)(v12 + 104);
  v51 = 0;
  v52 = 0;
  Source1 = 0;
  v50 = 0;
  LODWORD(CallBackContext) = 10;
  LOBYTE(Data) = v14;
  v45 = 0;
  v16 = SubmitControlRequest(161, (int)Descriptor, 5120, v6, Data, &v51, (size_t)CallBackContext, v11, v13);
  if ( v16 >= 0 )
  {
    if ( (unsigned __int16)v51 < WORD2(v51) && WORD1(v51) < HIWORD(v51) )
    {
      v50 = 0;
      v16 = ValidateRoiIspControlSetPayloadAndSummarizeRequestedSettings(
              a3,
              v52,
              v46,
              (unsigned int)&v50,
              (__int64)&v45);
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_42;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ebeb762af7253cd886177c9038d34848_Traceguids);
        goto LABEL_41;
      }
      if ( v50 )
      {
        v23 = SDWORD2(v45);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_DDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_ebeb762af7253cd886177c9038d34848_Traceguids,
              DWORD1(v45),
              v45,
              HIDWORD(v45),
              DWORD2(v45));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_DDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_ebeb762af7253cd886177c9038d34848_Traceguids,
              (unsigned __int16)v51,
              WORD1(v51),
              WORD2(v51),
              HIWORD(v51));
        }
        v24 = WORD2(v51);
        v25 = HIWORD(v51);
        v26 = WORD2(v51) - (unsigned int)(unsigned __int16)v51;
        v27 = (unsigned __int64)(unsigned __int16)v51 << 31;
        v28 = WORD2(v51);
        if ( (int)((__int64)(v27 + v26 * SDWORD1(v45)) / 0x80000000LL) < WORD2(v51) )
          v28 = (__int64)(v27 + v26 * SDWORD1(v45)) / 0x80000000LL;
        LOWORD(Source1) = v28;
        v47 = HIWORD(v51) - (unsigned int)WORD1(v51);
        v48 = (unsigned __int64)WORD1(v51) << 31;
        v29 = v27 + 0x7FFFFFFF;
        v21 = 1;
        v30 = HIWORD(v51);
        if ( (int)((__int64)(v48 + v47 * (int)v45) / 0x80000000LL) < HIWORD(v51) )
          v30 = (__int64)(v48 + v47 * (int)v45) / 0x80000000LL;
        WORD1(Source1) = v30;
        if ( (int)((__int64)(v26 * SHIDWORD(v45) + v29) / 0x80000000LL) < WORD2(v51) )
          v24 = (__int64)(v26 * SHIDWORD(v45) + v29) / 0x80000000LL;
        WORD2(Source1) = v24;
        v20 = (__int64)(v47 * v23 + v48 + 0x7FFFFFFF) / 0x80000000LL;
        if ( (int)v20 < HIWORD(v51) )
          v25 = (__int64)(v47 * v23 + v48 + 0x7FFFFFFF) / 0x80000000LL;
        HIWORD(Source1) = v25;
      }
      else
      {
        LODWORD(CallBackContexta) = 10;
        LOBYTE(v19) = v15;
        LOBYTE(v17) = -121;
        LOBYTE(v18) = -95;
        LOBYTE(Dataa) = v14;
        v16 = SubmitControlRequest(v18, v17, 5120, v19, Dataa, &Source1, (size_t)CallBackContexta, v11, v13);
        if ( v16 < 0 )
          goto LABEL_41;
        v22 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_34;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_ddddd(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_ebeb762af7253cd886177c9038d34848_Traceguids,
            (unsigned __int16)Source1,
            WORD1(Source1),
            WORD2(Source1),
            HIWORD(Source1),
            v50);
      }
      v22 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_ddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_ebeb762af7253cd886177c9038d34848_Traceguids,
          (unsigned __int16)Source1,
          WORD1(Source1),
          WORD2(Source1),
          HIWORD(Source1),
          v50);
LABEL_34:
      LODWORD(CallBackContexta) = 10;
      LOBYTE(v21) = v15;
      LOBYTE(v20) = 1;
      LOBYTE(v22) = 33;
      LOBYTE(Dataa) = v14;
      v16 = SubmitControlRequest(v22, v20, 5120, v21, Dataa, &Source1, (size_t)CallBackContexta, v11, v13);
      if ( v16 >= 0 )
      {
        Source2 = 0;
        LOBYTE(v33) = v15;
        v54 = 0;
        LOBYTE(v31) = -127;
        LOBYTE(v32) = -95;
        LODWORD(CallBackContextb) = 10;
        LOBYTE(Datab) = v14;
        v16 = SubmitControlRequest(v32, v31, 5120, v33, Datab, &Source2, (size_t)CallBackContextb, v11, v13);
        if ( v16 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_ddddd(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_ebeb762af7253cd886177c9038d34848_Traceguids,
              (unsigned __int16)Source2,
              WORD1(Source2),
              WORD2(Source2),
              HIWORD(Source2),
              v54);
          if ( RtlCompareMemory(&Source1, &Source2, 0xAu) == 10 )
          {
            v34 = *(unsigned int *)(a3 + 32);
            v35 = (void *)(v46 + 32);
            v36 = *(unsigned int *)(v46 + 32);
            *(_DWORD *)(v46 + 8) = *(_DWORD *)(a3 + 8);
            if ( (unsigned int)v36 > (unsigned int)v34 )
              memset(v35, 0, v36);
            memmove(v35, (const void *)(a3 + 32), v34);
            v37 = KsGetFilterFromIrp(Irp);
            KsGenerateEvents(v37, &KSEVENTSETID_ExtendedCameraControl, 0x16u, 0, 0, 0, 0);
            goto LABEL_41;
          }
          goto LABEL_48;
        }
      }
      goto LABEL_41;
    }
LABEL_48:
    v16 = -1073741823;
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_ebeb762af7253cd886177c9038d34848_Traceguids, (unsigned int)v16);
LABEL_42:
  Irp->IoStatus.Status = v16;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140007e70  mov     [rsp-8+arg_8], rbx
0x140007e75  push    rbp
0x140007e76  push    rsi
0x140007e77  push    rdi
0x140007e78  push    r12
0x140007e7a  push    r13
0x140007e7c  push    r14
0x140007e7e  push    r15
0x140007e80  lea     rbp, [rsp-27h]
0x140007e85  sub     rsp, 0B0h
0x140007e8c  mov     rax, cs:__security_cookie
0x140007e93  xor     rax, rsp
0x140007e96  mov     [rbp+57h+var_38], rax
0x140007e9a  mov     r14, r8
0x140007e9d  mov     rsi, rcx
0x140007ea0  call    cs:__imp_KsGetFilterFromIrp
0x140007ea7  nop     dword ptr [rax+rax+00h]
0x140007eac  test    rax, rax
0x140007eaf  jz      loc_1400083CB
0x140007eb5  mov     rcx, [rsi+0B8h]
0x140007ebc  mov     edx, [rcx+8]
0x140007ebf  test    edx, edx
0x140007ec1  jz      loc_1400083D5
0x140007ec7  cmp     edx, 30h ; '0'
0x140007eca  jb      loc_1400083E7
0x140007ed0  test    r14, r14
0x140007ed3  jz      loc_140008345
0x140007ed9  mov     r8d, [r14+8]
0x140007edd  cmp     edx, r8d
0x140007ee0  jb      loc_140008345
0x140007ee6  mov     rdx, [rax]
0x140007ee9  mov     r13, [rax+10h]
0x140007eed  mov     edi, [rdx+44h]
0x140007ef0  imul    edi, [r13+28h]
0x140007ef5  add     rdi, [rdx+48h]
0x140007ef9  mov     rcx, [rdi+0D8h]
0x140007f00  cmp     [rcx+5Ch], r8d
0x140007f04  jb      loc_140008345
0x140007f0a  mov     rax, [rdi+20h]
0x140007f0e  xorps   xmm0, xmm0
0x140007f11  mov     r13, [r13+0]
0x140007f15  mov     r8d, 1400h; int
0x140007f1b  mov     r12b, [rdi+28h]
0x140007f1f  mov     dl, 83h; int
0x140007f21  mov     [rsp+0E0h+var_A0], r13; __int64
0x140007f26  mov     r15b, [rax+3]
0x140007f2a  mov     rax, [rcx+68h]
0x140007f2e  mov     r9b, r15b; int
0x140007f31  xor     ecx, ecx
0x140007f33  mov     [rbp+57h+var_80], rax
0x140007f37  xor     eax, eax
0x140007f39  mov     [rsp+0E0h+var_A8], rdi; __int64
0x140007f3e  mov     [rbp+57h+var_58], rax
0x140007f42  mov     [rbp+57h+var_50], ax
0x140007f46  lea     rax, [rbp+57h+var_58]
0x140007f4a  mov     [rbp+57h+Source1], rcx
0x140007f4e  mov     [rbp+57h+var_60], cx
0x140007f52  mov     cl, 0A1h; int
0x140007f54  mov     dword ptr [rsp+0E0h+CallBackContext], 0Ah; Size
0x140007f5c  mov     [rsp+0E0h+CallBack], rax; void *
0x140007f61  mov     byte ptr [rsp+0E0h+Data], r12b; int
0x140007f66  movups  [rbp+57h+var_90], xmm0
0x140007f6a  call    SubmitControlRequest
0x140007f6f  xor     ecx, ecx
0x140007f71  mov     ebx, eax
0x140007f73  test    eax, eax
0x140007f75  js      loc_140008301
0x140007f7b  movzx   eax, word ptr [rbp+57h+var_58+4]
0x140007f7f  cmp     word ptr [rbp+57h+var_58], ax
0x140007f83  jnb     loc_1400083CB
0x140007f89  movzx   eax, word ptr [rbp+57h+var_58+6]
0x140007f8d  cmp     word ptr [rbp+57h+var_58+2], ax
0x140007f91  jnb     loc_1400083CB
0x140007f97  mov     r8, [rbp+57h+var_80]
0x140007f9b  lea     rax, [rbp+57h+var_90]
0x140007f9f  movzx   edx, [rbp+57h+var_50]
0x140007fa3  lea     r9, [rbp+57h+var_60]
0x140007fa7  mov     [rbp+57h+var_60], cx
0x140007fab  mov     rcx, r14
0x140007fae  mov     [rsp+0E0h+Data], rax
0x140007fb3  call    ValidateRoiIspControlSetPayloadAndSummarizeRequestedSettings
0x140007fb8  mov     ebx, eax
0x140007fba  xor     eax, eax
0x140007fbc  test    ebx, ebx
0x140007fbe  js      loc_1400083F1
0x140007fc4  cmp     [rbp+57h+var_60], ax
0x140007fc8  jnz     loc_140008070
0x140007fce  mov     [rsp+0E0h+var_A0], r13; __int64
0x140007fd3  lea     rax, [rbp+57h+Source1]
0x140007fd7  mov     [rsp+0E0h+var_A8], rdi; __int64
0x140007fdc  mov     r8d, 1400h; int
0x140007fe2  mov     dword ptr [rsp+0E0h+CallBackContext], 0Ah; Size
0x140007fea  mov     r9b, r15b; int
0x140007fed  mov     [rsp+0E0h+CallBack], rax; void *
0x140007ff2  mov     dl, 87h; int
0x140007ff4  mov     cl, 0A1h; int
0x140007ff6  mov     byte ptr [rsp+0E0h+Data], r12b; int
0x140007ffb  call    SubmitControlRequest
0x140008000  mov     ebx, eax
0x140008002  test    eax, eax
0x140008004  js      loc_140008301
0x14000800a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008011  lea     rbx, WPP_GLOBAL_Control
0x140008018  cmp     rcx, rbx
0x14000801b  jz      loc_1400081DE
0x140008021  cmp     byte ptr [rcx+29h], 4
0x140008025  jb      loc_1400081C8
0x14000802b  movzx   r8d, word ptr [rbp+57h+Source1+6]
0x140008030  mov     edx, 15h
0x140008035  movzx   eax, [rbp+57h+var_60]
0x140008039  movzx   r10d, word ptr [rbp+57h+Source1+4]
0x14000803e  movzx   r11d, word ptr [rbp+57h+Source1+2]
0x140008043  movzx   r9d, word ptr [rbp+57h+Source1]
0x140008048  mov     rcx, [rcx+18h]
0x14000804c  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140008050  mov     dword ptr [rsp+0E0h+CallBackContext], r8d
0x140008055  lea     r8, WPP_ebeb762af7253cd886177c9038d34848_Traceguids
0x14000805c  mov     dword ptr [rsp+0E0h+CallBack], r10d
0x140008061  mov     dword ptr [rsp+0E0h+Data], r11d
0x140008066  call    WPP_SF_ddddd
0x14000806b  jmp     loc_1400081C8
0x140008070  mov     rcx, cs:WPP_GLOBAL_Control
0x140008077  lea     rax, WPP_GLOBAL_Control
0x14000807e  movsxd  rbx, dword ptr [rbp+57h+var_90+8]
0x140008082  cmp     rcx, rax
0x140008085  jz      short loc_1400080A7
0x140008087  cmp     byte ptr [rcx+29h], 4
0x14000808b  jnb     loc_14000842C
0x140008091  mov     rcx, cs:WPP_GLOBAL_Control
0x140008098  cmp     rcx, rax
0x14000809b  jz      short loc_1400080A7
0x14000809d  cmp     byte ptr [rcx+29h], 4
0x1400080a1  jnb     loc_140008463
0x1400080a7  movzx   r11d, word ptr [rbp+57h+var_58+4]
0x1400080ac  mov     rax, 8000000000000001h
0x1400080b6  movzx   r9d, word ptr [rbp+57h+var_58]
0x1400080bb  mov     r8d, r11d
0x1400080be  movzx   r10d, word ptr [rbp+57h+var_58+6]
0x1400080c3  sub     r8d, r9d
0x1400080c6  movsxd  rcx, dword ptr [rbp+57h+var_90+4]
0x1400080ca  imul    rcx, r8
0x1400080ce  shl     r9, 1Fh
0x1400080d2  add     rcx, r9
0x1400080d5  imul    rcx
0x1400080d8  add     rdx, rcx
0x1400080db  movsxd  rcx, dword ptr [rbp+57h+var_90]
0x1400080df  sar     rdx, 1Eh
0x1400080e3  mov     rax, rdx
0x1400080e6  shr     rax, 3Fh
0x1400080ea  add     rdx, rax
0x1400080ed  movzx   eax, r11w
0x1400080f1  cmp     edx, r11d
0x1400080f4  cmovl   ax, dx
0x1400080f8  movzx   edx, word ptr [rbp+57h+var_58+2]
0x1400080fc  mov     word ptr [rbp+57h+Source1], ax
0x140008100  mov     eax, r10d
0x140008103  sub     eax, edx
0x140008105  shl     rdx, 1Fh
0x140008109  imul    rcx, rax
0x14000810d  mov     [rbp+57h+var_78], rax
0x140008111  mov     rax, 8000000000000001h
0x14000811b  add     rcx, rdx
0x14000811e  mov     [rbp+57h+var_70], rdx
0x140008122  imul    rcx
0x140008125  add     rdx, rcx
0x140008128  lea     rcx, [r9+7FFFFFFFh]
0x14000812f  sar     rdx, 1Eh
0x140008133  mov     r9, 8000000000000001h
0x14000813d  mov     rax, rdx
0x140008140  shr     rax, 3Fh
0x140008144  add     rdx, rax
0x140008147  movzx   eax, r10w
0x14000814b  cmp     edx, r10d
0x14000814e  cmovl   ax, dx
0x140008152  mov     word ptr [rbp+57h+Source1+2], ax
0x140008156  movsxd  rax, dword ptr [rbp+57h+var_90+0Ch]
0x14000815a  imul    rax, r8
0x14000815e  add     rcx, rax
0x140008161  mov     rax, r9
0x140008164  imul    rcx
0x140008167  add     rdx, rcx
0x14000816a  sar     rdx, 1Eh
0x14000816e  mov     rax, rdx
0x140008171  shr     rax, 3Fh
0x140008175  add     rdx, rax
0x140008178  cmp     edx, r11d
0x14000817b  jge     short loc_140008181
0x14000817d  movzx   r11d, dx
0x140008181  mov     r8, [rbp+57h+var_70]
0x140008185  mov     rcx, rbx
0x140008188  imul    rcx, [rbp+57h+var_78]
0x14000818d  add     r8, 7FFFFFFFh
0x140008194  mov     word ptr [rbp+57h+Source1+4], r11w
0x140008199  add     r8, rcx
0x14000819c  mov     rax, r9
0x14000819f  imul    r8
0x1400081a2  add     rdx, r8
0x1400081a5  sar     rdx, 1Eh
0x1400081a9  mov     rax, rdx
0x1400081ac  shr     rax, 3Fh
0x1400081b0  add     rdx, rax
0x1400081b3  cmp     edx, r10d
0x1400081b6  jl      loc_1400083C2
0x1400081bc  mov     word ptr [rbp+57h+Source1+6], r10w
0x1400081c1  lea     rbx, WPP_GLOBAL_Control
0x1400081c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081cf  cmp     rcx, rbx
0x1400081d2  jz      short loc_1400081DE
0x1400081d4  cmp     byte ptr [rcx+29h], 4
0x1400081d8  jnb     loc_14000849E
0x1400081de  mov     [rsp+0E0h+var_A0], r13; __int64
0x1400081e3  lea     rax, [rbp+57h+Source1]
0x1400081e7  mov     [rsp+0E0h+var_A8], rdi; __int64
0x1400081ec  mov     r8d, 1400h; int
0x1400081f2  mov     dword ptr [rsp+0E0h+CallBackContext], 0Ah; Size
0x1400081fa  mov     r9b, r15b; int
0x1400081fd  mov     [rsp+0E0h+CallBack], rax; void *
0x140008202  mov     dl, 1; int
0x140008204  mov     cl, 21h ; '!'; int
0x140008206  mov     byte ptr [rsp+0E0h+Data], r12b; int
0x14000820b  call    SubmitControlRequest
0x140008210  mov     ebx, eax
0x140008212  test    eax, eax
0x140008214  js      loc_140008301
0x14000821a  xor     eax, eax
0x14000821c  mov     [rsp+0E0h+var_A0], r13; __int64
0x140008221  mov     [rsp+0E0h+var_A8], rdi; __int64
0x140008226  mov     r8d, 1400h; int
0x14000822c  mov     [rbp+57h+Source2], rax
0x140008230  mov     r9b, r15b; int
0x140008233  mov     [rbp+57h+var_40], ax
0x140008237  mov     dl, 81h; int
0x140008239  lea     edi, [rax+0Ah]
0x14000823c  mov     cl, 0A1h; int
0x14000823e  lea     rax, [rbp+57h+Source2]
0x140008242  mov     dword ptr [rsp+0E0h+CallBackContext], edi; Size
0x140008246  mov     [rsp+0E0h+CallBack], rax; void *
0x14000824b  mov     byte ptr [rsp+0E0h+Data], r12b; int
0x140008250  call    SubmitControlRequest
0x140008255  xor     r13d, r13d
0x140008258  mov     ebx, eax
0x14000825a  test    eax, eax
0x14000825c  js      loc_140008301
0x140008262  mov     rcx, cs:WPP_GLOBAL_Control
0x140008269  lea     rax, WPP_GLOBAL_Control
0x140008270  cmp     rcx, rax
0x140008273  jnz     loc_14000834C
0x140008279  mov     r8, rdi; Length
0x14000827c  lea     rdx, [rbp+57h+Source2]; Source2
0x140008280  lea     rcx, [rbp+57h+Source1]; Source1
0x140008284  call    cs:__imp_RtlCompareMemory
0x14000828b  nop     dword ptr [rax+rax+00h]
0x140008290  cmp     rax, rdi
0x140008293  jnz     loc_1400083CB
0x140008299  mov     rdx, [rbp+57h+var_80]
0x14000829d  mov     r12d, [r14+20h]
0x1400082a1  mov     eax, [r14+8]
0x1400082a5  lea     rdi, [rdx+20h]
0x1400082a9  mov     ecx, [rdi]
0x1400082ab  mov     [rdx+8], eax
0x1400082ae  cmp     ecx, r12d
0x1400082b1  ja      loc_1400084E3
0x1400082b7  mov     r8, r12; Size
0x1400082ba  lea     rdx, [r14+20h]; Src
0x1400082be  mov     rcx, rdi; void *
0x1400082c1  call    memmove
0x1400082c6  mov     rcx, rsi; Irp
0x1400082c9  call    cs:__imp_KsGetFilterFromIrp
0x1400082d0  nop     dword ptr [rax+rax+00h]
0x1400082d5  xor     r9d, r9d; DataSize
0x1400082d8  mov     [rsp+0E0h+CallBackContext], r13; CallBackContext
0x1400082dd  mov     rcx, rax; Object
0x1400082e0  mov     [rsp+0E0h+CallBack], r13; CallBack
0x1400082e5  lea     rdx, KSEVENTSETID_ExtendedCameraControl; EventSet
0x1400082ec  mov     [rsp+0E0h+Data], r13; Data
0x1400082f1  lea     r8d, [r9+16h]; EventId
0x1400082f5  call    cs:__imp_KsGenerateEvents
0x1400082fc  nop     dword ptr [rax+rax+00h]
0x140008301  lea     rdi, WPP_GLOBAL_Control
0x140008308  mov     rcx, cs:WPP_GLOBAL_Control
0x14000830f  cmp     rcx, rdi
0x140008312  jnz     loc_14000839B
0x140008318  mov     [rsi+30h], ebx
0x14000831b  mov     eax, ebx
0x14000831d  mov     rcx, [rbp+57h+var_38]
0x140008321  xor     rcx, rsp; StackCookie
0x140008324  call    __security_check_cookie
0x140008329  mov     rbx, [rsp+0E0h+arg_8]
0x140008331  add     rsp, 0B0h
0x140008338  pop     r15
0x14000833a  pop     r14
0x14000833c  pop     r13
0x14000833e  pop     r12
0x140008340  pop     rdi
0x140008341  pop     rsi
0x140008342  pop     rbp
0x140008343  retn
0x140008345  mov     ebx, 0C000000Dh
0x14000834a  jmp     short loc_140008301
0x14000834c  cmp     byte ptr [rcx+29h], 4
  ... truncated ...
```
