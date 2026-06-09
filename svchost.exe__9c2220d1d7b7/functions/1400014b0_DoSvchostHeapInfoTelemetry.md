# DoSvchostHeapInfoTelemetry

- ea: `0x1400014b0`
- end: `0x1400018f6`
- name: `DoSvchostHeapInfoTelemetry`
- size: `1094`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001070`
- `0x1400086f8`

## callees

- `0x1400014b0`
- `0x140004f90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001877`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001877`

## pseudocode

```c
void DoSvchostHeapInfoTelemetry()
{
  unsigned int i; // edi
  __int64 v1; // rbx
  unsigned __int64 v2; // rax
  _QWORD *v3; // rdx
  char *v4; // rcx
  __int64 v5; // rax
  bool v6; // zf
  int v7; // eax
  __int64 v8; // rax
  EVENT_DESCRIPTOR *p_EventDescriptor; // rdx
  struct _EVENT_DATA_DESCRIPTOR *UserData; // rax
  _QWORD *v11; // rdx
  char *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  bool v16; // [rsp+38h] [rbp-D0h] BYREF
  bool v17; // [rsp+39h] [rbp-CFh] BYREF
  unsigned int v18; // [rsp+3Ch] [rbp-CCh]
  int v19; // [rsp+40h] [rbp-C8h] BYREF
  int v20; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v21; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h] BYREF
  _DWORD v29[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v30; // [rsp+90h] [rbp-78h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+A8h] [rbp-60h] BYREF
  void *v33; // [rsp+B8h] [rbp-50h]
  int v34; // [rsp+C0h] [rbp-48h]
  int v35; // [rsp+C4h] [rbp-44h]
  __int64 *v36; // [rsp+C8h] [rbp-40h]
  __int64 v37; // [rsp+D0h] [rbp-38h]
  char *v38; // [rsp+D8h] [rbp-30h]
  int v39; // [rsp+E0h] [rbp-28h]
  int v40; // [rsp+E4h] [rbp-24h]
  __int64 *v41; // [rsp+E8h] [rbp-20h]
  __int64 v42; // [rsp+F0h] [rbp-18h]
  __int64 *v43; // [rsp+F8h] [rbp-10h]
  __int64 v44; // [rsp+100h] [rbp-8h]
  __int64 *v45; // [rsp+108h] [rbp+0h]
  __int64 v46; // [rsp+110h] [rbp+8h]
  bool *v47; // [rsp+118h] [rbp+10h]
  __int64 v48; // [rsp+120h] [rbp+18h]
  int *v49; // [rsp+128h] [rbp+20h]
  __int64 v50; // [rsp+130h] [rbp+28h]
  void *v51; // [rsp+138h] [rbp+30h] BYREF
  int v52; // [rsp+140h] [rbp+38h]
  int v53; // [rsp+144h] [rbp+3Ch]
  void *v54; // [rsp+148h] [rbp+40h]
  int v55; // [rsp+150h] [rbp+48h]
  int v56; // [rsp+154h] [rbp+4Ch]
  __int64 *v57; // [rsp+158h] [rbp+50h]
  __int64 v58; // [rsp+160h] [rbp+58h]
  char *v59; // [rsp+168h] [rbp+60h]
  int v60; // [rsp+170h] [rbp+68h]
  int v61; // [rsp+174h] [rbp+6Ch]
  __int64 *v62; // [rsp+178h] [rbp+70h]
  __int64 v63; // [rsp+180h] [rbp+78h]
  __int64 *v64; // [rsp+188h] [rbp+80h]
  __int64 v65; // [rsp+190h] [rbp+88h]
  __int64 *v66; // [rsp+198h] [rbp+90h]
  __int64 v67; // [rsp+1A0h] [rbp+98h]
  bool *v68; // [rsp+1A8h] [rbp+A0h]
  __int64 v69; // [rsp+1B0h] [rbp+A8h]
  int *v70; // [rsp+1B8h] [rbp+B0h]
  __int64 v71; // [rsp+1C0h] [rbp+B8h]

  for ( i = 0; i < ServiceCount; ++i )
  {
    v1 = 96LL * i;
    if ( !*(_DWORD *)(v1 + ServiceArray + 48) )
      continue;
    v2 = *(_QWORD *)(v1 + ServiceArray + 64);
    if ( !v2 )
      continue;
    if ( (unsigned int)(v2 >> 10) < g_HeapReportingThresholdKb )
    {
      if ( (unsigned int)dword_14000F000 <= 5
        || (qword_14000F010 & 0x200000000000LL) == 0
        || (qword_14000F018 & 0x200000000000LL) != qword_14000F018 )
      {
        goto LABEL_24;
      }
      v11 = (_QWORD *)(v1 + ServiceArray);
      v25 = 0x1000000;
      v57 = &v25;
      v58 = 8;
      v12 = *(char **)(v1 + ServiceArray);
      if ( v12 )
      {
        v13 = -1;
        do
          v6 = *(_WORD *)&v12[2 * v13++ + 2] == 0;
        while ( !v6 );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v12 = "";
        v14 = 2;
      }
      v60 = v14;
      v59 = v12;
      v61 = 0;
      v26 = v11[8];
      v62 = &v26;
      v63 = 8;
      v27 = v11[7];
      v64 = &v27;
      v65 = 8;
      v15 = v11[9];
      v17 = ServiceCount == 1;
      v28 = v15;
      p_EventDescriptor = &EventDescriptor;
      v67 = 8;
      v66 = &v28;
      v68 = &v17;
      v20 = TelemetryState;
      v70 = &v20;
      *(_DWORD *)&EventDescriptor.Level = 5;
      v51 = off_14000F008;
      v69 = 1;
      v71 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x200000000000LL;
      v52 = *(unsigned __int16 *)off_14000F008;
      v53 = 2;
      v54 = &unk_14000BC2B;
      v55 = 123;
      v56 = 1;
      v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      UserData = (struct _EVENT_DATA_DESCRIPTOR *)&v51;
    }
    else
    {
      if ( (unsigned int)dword_14000F000 <= 5
        || (qword_14000F010 & 0x400000000000LL) == 0
        || (qword_14000F018 & 0x400000000000LL) != qword_14000F018 )
      {
        goto LABEL_24;
      }
      v3 = (_QWORD *)(v1 + ServiceArray);
      v21 = 0x1000000;
      v36 = &v21;
      v37 = 8;
      v4 = *(char **)(v1 + ServiceArray);
      if ( v4 )
      {
        v5 = -1;
        do
          v6 = *(_WORD *)&v4[2 * v5++ + 2] == 0;
        while ( !v6 );
        v7 = 2 * v5 + 2;
      }
      else
      {
        v4 = "";
        v7 = 2;
      }
      v39 = v7;
      v38 = v4;
      v40 = 0;
      v22 = v3[8];
      v41 = &v22;
      v42 = 8;
      v23 = v3[7];
      v43 = &v23;
      v44 = 8;
      v8 = v3[9];
      v16 = ServiceCount == 1;
      v24 = v8;
      p_EventDescriptor = (EVENT_DESCRIPTOR *)v29;
      v46 = 8;
      v45 = &v24;
      v47 = &v16;
      v19 = TelemetryState;
      v49 = &v19;
      v29[1] = 5;
      v32.Ptr = (ULONGLONG)off_14000F008;
      v48 = 1;
      v50 = 4;
      v29[0] = 184549376;
      v30 = 0x400000000000LL;
      v32.Size = *(unsigned __int16 *)off_14000F008;
      v32.Reserved = 2;
      v33 = &unk_14000BCB2;
      v34 = 123;
      v35 = 1;
      v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      UserData = &v32;
    }
    EventWriteTransfer(RegHandle, p_EventDescriptor, 0, 0, 9u, UserData);
LABEL_24:
    if ( !TelemetryState )
      *(_QWORD *)(v1 + ServiceArray + 56) = 0;
  }
}

```

## disassembly

```asm
0x1400014b0  mov     r11, rsp
0x1400014b3  push    rbp
0x1400014b4  push    rsi
0x1400014b5  push    rdi
0x1400014b6  lea     rbp, [r11-0F8h]
0x1400014bd  sub     rsp, 1E0h
0x1400014c4  mov     rax, cs:__security_cookie
0x1400014cb  xor     rax, rsp
0x1400014ce  mov     [rbp+0F0h+var_30], rax
0x1400014d5  xor     esi, esi
0x1400014d7  cmp     cs:ServiceCount, esi
0x1400014dd  mov     edi, esi
0x1400014df  jbe     loc_1400018DB
0x1400014e5  mov     [r11+8], rbx
0x1400014e9  lea     r8, unk_14000BCB2
0x1400014f0  mov     [r11+10h], r12
0x1400014f4  lea     r9, unk_14000BC2B
0x1400014fb  mov     [r11+18h], r13
0x1400014ff  lea     r12, _TraceLoggingMetadataEnd
0x140001506  mov     [r11-20h], r14
0x14000150a  lea     r13, _TraceLoggingMetadata
0x140001511  mov     [r11-28h], r15
0x140001515  mov     r14, 400000000000h
0x14000151f  mov     r15, 200000000000h
0x140001529  nop     dword ptr [rax+00000000h]
0x140001530  mov     eax, edi
0x140001532  lea     rbx, [rax+rax*2]
0x140001536  mov     rax, cs:ServiceArray
0x14000153d  shl     rbx, 5
0x140001541  cmp     [rbx+rax+30h], esi
0x140001545  jz      loc_1400018A5
0x14000154b  mov     rax, [rbx+rax+40h]
0x140001550  test    rax, rax
0x140001553  jz      loc_1400018A5
0x140001559  shr     rax, 0Ah
0x14000155d  cmp     eax, cs:g_HeapReportingThresholdKb
0x140001563  mov     eax, cs:dword_14000F000
0x140001569  jb      loc_1400016DB
0x14000156f  cmp     eax, 5
0x140001572  jbe     loc_140001883
0x140001578  mov     rcx, cs:qword_14000F018
0x14000157f  mov     rax, cs:qword_14000F010
0x140001586  test    r14, rax
0x140001589  jz      loc_140001883
0x14000158f  mov     rax, rcx
0x140001592  and     rax, r14
0x140001595  cmp     rax, rcx
0x140001598  jnz     loc_140001883
0x14000159e  mov     rdx, cs:ServiceArray
0x1400015a5  lea     rax, [rsp+1F0h+var_1B0]
0x1400015aa  add     rdx, rbx
0x1400015ad  mov     [rsp+1F0h+var_1B0], 1000000h
0x1400015b6  mov     [rbp+0F0h+var_130], rax
0x1400015ba  mov     [rbp+0F0h+var_128], 8
0x1400015c2  mov     rcx, [rdx]
0x1400015c5  test    rcx, rcx
0x1400015c8  jz      short loc_1400015E5
0x1400015ca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400015d1  cmp     [rcx+rax*2+2], si
0x1400015d6  lea     rax, [rax+1]
0x1400015da  jnz     short loc_1400015D1
0x1400015dc  lea     eax, ds:2[rax*2]
0x1400015e3  jmp     short loc_1400015F1
0x1400015e5  lea     rcx, aNourlmimefilte+10h; ""
0x1400015ec  mov     eax, 2
0x1400015f1  cmp     cs:ServiceCount, 1
0x1400015f8  mov     [rbp+0F0h+var_118], eax
0x1400015fb  mov     [rbp+0F0h+var_120], rcx
0x1400015ff  mov     [rbp+0F0h+var_114], esi
0x140001602  mov     rax, [rdx+40h]
0x140001606  mov     [rsp+1F0h+var_1A8], rax
0x14000160b  lea     rax, [rsp+1F0h+var_1A8]
0x140001610  mov     [rbp+0F0h+var_110], rax
0x140001614  mov     [rbp+0F0h+var_108], 8
0x14000161c  mov     rax, [rdx+38h]
0x140001620  mov     [rsp+1F0h+var_1A0], rax
0x140001625  lea     rax, [rsp+1F0h+var_1A0]
0x14000162a  mov     [rbp+0F0h+var_100], rax
0x14000162e  mov     [rbp+0F0h+var_F8], 8
0x140001636  mov     rax, [rdx+48h]
0x14000163a  setz    byte ptr [rsp+1F0h+var_1C0]
0x14000163f  mov     [rsp+1F0h+var_198], rax
0x140001644  lea     rdx, [rbp+0F0h+var_170]
0x140001648  lea     rax, [rsp+1F0h+var_198]
0x14000164d  mov     [rbp+0F0h+var_E8], 8
0x140001655  mov     [rbp+0F0h+var_F0], rax
0x140001659  lea     rax, [rsp+1F0h+var_1C0]
0x14000165e  mov     [rbp+0F0h+var_E0], rax
0x140001662  mov     eax, cs:TelemetryState
0x140001668  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x14000166c  lea     rax, [rsp+1F0h+var_1B8]
0x140001671  mov     [rbp+0F0h+var_D0], rax
0x140001675  movzx   eax, cs:word_14000BCA8
0x14000167c  mov     [rbp+0F0h+var_16C], eax
0x14000167f  mov     rax, cs:off_14000F008
0x140001686  mov     [rbp+0F0h+var_150.Ptr], rax
0x14000168a  mov     [rbp+0F0h+var_D8], 1
0x140001692  mov     [rbp+0F0h+var_C8], 4
0x14000169a  mov     [rbp+0F0h+var_170], 0B000000h
0x1400016a1  mov     [rbp+0F0h+var_168], r14
0x1400016a5  movzx   eax, word ptr [rax]
0x1400016a8  mov     [rbp+0F0h+var_150.Size], eax
0x1400016ab  mov     rax, r12
0x1400016ae  sub     eax, r13d
0x1400016b1  mov     dword ptr [rbp+0F0h+var_150.0Ch], 2
0x1400016b8  mov     [rbp+0F0h+var_140], r8
0x1400016bc  mov     [rbp+0F0h+var_138], 7Bh ; '{'
0x1400016c3  mov     [rbp+0F0h+var_134], 1
0x1400016ca  mov     [rsp+1F0h+var_1BC], eax
0x1400016ce  mov     eax, [rsp+1F0h+var_1BC]
0x1400016d2  lea     rax, [rbp+0F0h+var_150]
0x1400016d6  jmp     loc_14000185D
0x1400016db  cmp     eax, 5
0x1400016de  jbe     loc_140001883
0x1400016e4  mov     rcx, cs:qword_14000F018
0x1400016eb  mov     rax, cs:qword_14000F010
0x1400016f2  test    r15, rax
0x1400016f5  jz      loc_140001883
0x1400016fb  mov     rax, rcx
0x1400016fe  and     rax, r15
0x140001701  cmp     rax, rcx
0x140001704  jnz     loc_140001883
0x14000170a  mov     rdx, cs:ServiceArray
0x140001711  lea     rax, [rsp+1F0h+var_190]
0x140001716  add     rdx, rbx
0x140001719  mov     [rsp+1F0h+var_190], 1000000h
0x140001722  mov     [rbp+0F0h+var_A0], rax
0x140001726  mov     [rbp+0F0h+var_98], 8
0x14000172e  mov     rcx, [rdx]
0x140001731  test    rcx, rcx
0x140001734  jz      short loc_140001754
0x140001736  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000173d  nop     dword ptr [rax]
0x140001740  cmp     [rcx+rax*2+2], si
0x140001745  lea     rax, [rax+1]
0x140001749  jnz     short loc_140001740
0x14000174b  lea     eax, ds:2[rax*2]
0x140001752  jmp     short loc_140001760
0x140001754  lea     rcx, aNourlmimefilte+10h; ""
0x14000175b  mov     eax, 2
0x140001760  cmp     cs:ServiceCount, 1
0x140001767  mov     [rbp+0F0h+var_88], eax
0x14000176a  mov     [rbp+0F0h+var_90], rcx
0x14000176e  mov     [rbp+0F0h+var_84], esi
0x140001771  mov     rax, [rdx+40h]
0x140001775  mov     [rsp+1F0h+var_188], rax
0x14000177a  lea     rax, [rsp+1F0h+var_188]
0x14000177f  mov     [rbp+0F0h+var_80], rax
0x140001783  mov     [rbp+0F0h+var_78], 8
0x14000178b  mov     rax, [rdx+38h]
0x14000178f  mov     [rsp+1F0h+var_180], rax
0x140001794  lea     rax, [rsp+1F0h+var_180]
0x140001799  mov     [rbp+0F0h+var_70], rax
0x1400017a0  mov     [rbp+0F0h+var_68], 8
0x1400017ab  mov     rax, [rdx+48h]
0x1400017af  setz    byte ptr [rsp+1F0h+var_1C0+1]
0x1400017b4  mov     [rsp+1F0h+var_178], rax
0x1400017b9  lea     rdx, [rbp+0F0h+EventDescriptor]; EventDescriptor
0x1400017bd  lea     rax, [rsp+1F0h+var_178]
0x1400017c2  mov     [rbp+0F0h+var_58], 8
0x1400017cd  mov     [rbp+0F0h+var_60], rax
0x1400017d4  lea     rax, [rsp+1F0h+var_1C0+1]
0x1400017d9  mov     [rbp+0F0h+var_50], rax
0x1400017e0  mov     eax, cs:TelemetryState
0x1400017e6  mov     dword ptr [rsp+1F0h+var_1B8+4], eax
0x1400017ea  lea     rax, [rsp+1F0h+var_1B8+4]
0x1400017ef  mov     [rbp+0F0h+var_40], rax
0x1400017f6  movzx   eax, cs:word_14000BC21
0x1400017fd  mov     dword ptr [rbp+0F0h+EventDescriptor.Level], eax
0x140001800  mov     rax, cs:off_14000F008
0x140001807  mov     [rbp+0F0h+var_C0], rax
0x14000180b  mov     [rbp+0F0h+var_48], 1
0x140001816  mov     [rbp+0F0h+var_38], 4
0x140001821  mov     dword ptr [rbp+0F0h+EventDescriptor.Id], 0B000000h
0x140001828  mov     [rbp+0F0h+EventDescriptor.Keyword], r15
0x14000182c  movzx   eax, word ptr [rax]
0x14000182f  mov     [rbp+0F0h+var_B8], eax
0x140001832  mov     rax, r12
0x140001835  sub     eax, r13d
0x140001838  mov     [rbp+0F0h+var_B4], 2
0x14000183f  mov     [rbp+0F0h+var_B0], r9
0x140001843  mov     [rbp+0F0h+var_A8], 7Bh ; '{'
0x14000184a  mov     [rbp+0F0h+var_A4], 1
0x140001851  mov     [rsp+1F0h+var_1BC], eax
0x140001855  mov     eax, [rsp+1F0h+var_1BC]
0x140001859  lea     rax, [rbp+0F0h+var_C0]
0x14000185d  mov     rcx, cs:RegHandle; RegHandle
0x140001864  xor     r9d, r9d; RelatedActivityId
0x140001867  mov     [rsp+1F0h+UserData], rax; UserData
0x14000186c  xor     r8d, r8d; ActivityId
0x14000186f  mov     [rsp+1F0h+UserDataCount], 9; UserDataCount
0x140001877  call    cs:__imp_EventWriteTransfer
0x14000187e  nop     dword ptr [rax+rax+00h]
0x140001883  cmp     cs:TelemetryState, esi
0x140001889  lea     r8, unk_14000BCB2
0x140001890  lea     r9, unk_14000BC2B
0x140001897  jnz     short loc_1400018A5
0x140001899  mov     rax, cs:ServiceArray
0x1400018a0  mov     [rbx+rax+38h], rsi
0x1400018a5  inc     edi
0x1400018a7  cmp     edi, cs:ServiceCount
0x1400018ad  jb      loc_140001530
0x1400018b3  mov     r15, [rsp+1F0h+var_20]
0x1400018bb  mov     r14, [rsp+1D8h]
0x1400018c3  mov     r13, [rsp+1F0h+arg_10]
0x1400018cb  mov     r12, [rsp+1F0h+arg_8]
0x1400018d3  mov     rbx, [rsp+1F0h+arg_0]
0x1400018db  mov     rcx, [rbp+0F0h+var_30]
0x1400018e2  xor     rcx, rsp; StackCookie
0x1400018e5  call    __security_check_cookie
0x1400018ea  add     rsp, 1E0h
0x1400018f1  pop     rdi
0x1400018f2  pop     rsi
0x1400018f3  pop     rbp
0x1400018f4  retn
```
