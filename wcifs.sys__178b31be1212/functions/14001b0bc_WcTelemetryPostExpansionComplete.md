# WcTelemetryPostExpansionComplete

- ea: `0x14001b0bc`
- end: `0x14001b51e`
- name: `WcTelemetryPostExpansionComplete`
- size: `1122`
- prototype: `char __fastcall(__int64, __int64, int, int, __int64, unsigned __int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400184f0`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400020c4`
- `0x1400053f8`
- `0x140005c0c`
- `0x140007ad4`
- `0x140007c60`
- `0x14001b0bc`

## pseudocode

```c
char __fastcall WcTelemetryPostExpansionComplete(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10)
{
  unsigned __int128 v10; // rax
  __int64 v12; // rbx
  int v14; // r15d
  __int64 v15; // r10
  int v16; // edi
  int v17; // r11d
  const WCHAR *v18; // rax
  unsigned __int16 v19; // dx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r10
  __int64 v25; // [rsp+38h] [rbp-C8h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+74h] [rbp-8Ch] BYREF
  int v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  __int64 *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  const WCHAR *v43; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+118h] [rbp+18h] BYREF
  __int64 *v45; // [rsp+120h] [rbp+20h]
  __int64 v46; // [rsp+128h] [rbp+28h]
  __int64 *v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+138h] [rbp+38h]
  __int64 *v49; // [rsp+140h] [rbp+40h]
  __int64 v50; // [rsp+148h] [rbp+48h]
  unsigned __int64 *v51; // [rsp+150h] [rbp+50h]
  __int64 v52; // [rsp+158h] [rbp+58h]
  __int64 *v53; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]

  *((_QWORD *)&v10 + 1) = a2;
  *(_QWORD *)&v10 = *(_QWORD *)(a10 + 240);
  v12 = a6;
  v14 = BYTE8(v10);
  v33 = 0;
  v15 = *(_QWORD *)(v10 + 64);
  WORD1(v33) = *(_WORD *)(v15 + 32);
  LOWORD(v33) = WORD1(v33);
  *((_QWORD *)&v33 + 1) = v15 + 34;
  *(_QWORD *)&v10 = WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids;
  if ( a4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      BYTE8(v10) = 2;
      LOBYTE(v10) = WPP_RECORDER_SF_sDqd(
                      wil_details_featureDescriptors_a->DeviceExtension,
                      WORD4(v10),
                      10,
                      14,
                      (__int64)WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\wcifs\\telemetry.c",
                      250,
                      a1,
                      a4);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = (_BYTE)wil_details_featureDescriptors_a;
    if ( LOWORD(wil_details_featureDescriptors_a->DeviceType) )
    {
      HIDWORD(v25) = HIDWORD(a1);
      LOBYTE(v10) = WPP_RECORDER_SF_sDqLiLZii(
                      a1,
                      WORD4(v10),
                      (unsigned int)"onecore\\base\\fs\\wci\\wcifs\\telemetry.c",
                      a10);
    }
  }
  v16 = a3 - 1;
  if ( v16 )
  {
    if ( v16 == 1 )
    {
      LOBYTE(v10) = dword_14000E060;
      if ( (unsigned int)dword_14000E060 > 5 )
      {
        LOBYTE(v10) = tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL);
        if ( (_BYTE)v10 )
        {
          v26 = a4;
          v37 = (__int64 *)&v26;
          v39 = (unsigned __int64 *)&v27;
          v18 = (const WCHAR *)*((_QWORD *)&v33 + 1);
          v38 = 4;
          v27 = v14;
          v40 = 4;
          if ( *((_QWORD *)&v33 + 1) )
          {
            v19 = v33;
          }
          else
          {
            v18 = &word_14000A898;
            v19 = v17;
          }
          v43 = v18;
          LODWORD(v44) = v19;
          v28 = *(_DWORD *)(a10 + 252);
          v45 = (__int64 *)&v28;
          v29 = *(_QWORD *)(a10 + 256);
          v47 = &v29;
          v30 = a5;
          v49 = &v30;
          v51 = &v31;
          v53 = &v32;
          v41 = &v44;
          v42 = 2;
          HIDWORD(v44) = v17;
          v46 = 4;
          v48 = 8;
          v50 = 8;
          v31 = a6;
          v52 = 8;
          v32 = a7;
          v54 = 8;
          LOBYTE(v10) = tlgWriteTransfer_EtwWriteTransfer(
                          (__int64)&dword_14000E060,
                          (unsigned __int8 *)&unk_14000B898,
                          0,
                          0,
                          0xBu,
                          &v36);
        }
      }
    }
  }
  else if ( a4 >= 0 && !(_BYTE)v14 )
  {
    if ( a6 >= 0x400 )
    {
      if ( a6 >= 0x100000 )
      {
        if ( a6 >= 0x40000000 )
          v12 = a6 >> 30;
        else
          v12 = a6 >> 20;
      }
      else
      {
        v12 = a6 >> 10;
      }
    }
    v34 = 0;
    v10 = (unsigned __int64)v12 * (unsigned __int128)(unsigned __int64)v12;
    if ( is_mul_ok(v12, v12) )
    {
      if ( (unsigned int)dword_14000E060 > 5 )
      {
        LOBYTE(v10) = tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL);
        if ( (_BYTE)v10 )
        {
          v32 = 1;
          v37 = &v32;
          v38 = 8;
          v39 = &v31;
          v41 = &v30;
          v43 = (const WCHAR *)&v29;
          v45 = &v35;
          v47 = (__int64 *)&v28;
          v27 = a8;
          v49 = (__int64 *)&v27;
          v26 = a9;
          v51 = (unsigned __int64 *)&v26;
          v53 = &v34;
          v31 = v12;
          v40 = 8;
          v30 = v23;
          v42 = 8;
          v29 = v12;
          v44 = 8;
          v35 = v12;
          v46 = 8;
          v28 = v22;
          v48 = 4;
          v50 = 4;
          v52 = 4;
          v34 = 0x1000000;
          v54 = 8;
          LOBYTE(v10) = tlgWriteAgg(v20, (unsigned __int8 *)&byte_14000B961, v21, v22, &v36);
        }
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v25) = -1073741675;
      BYTE8(v10) = 3;
      LOBYTE(v10) = WPP_RECORDER_SF_sDd(
                      wil_details_featureDescriptors_a->DeviceExtension,
                      DWORD2(v10),
                      10,
                      15,
                      (__int64)WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\wcifs\\telemetry.c",
                      70,
                      v25);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14001b0bc  mov     [rsp-8+arg_8], rbx
0x14001b0c1  push    rbp
0x14001b0c2  push    rsi
0x14001b0c3  push    rdi
0x14001b0c4  push    r12
0x14001b0c6  push    r13
0x14001b0c8  push    r14
0x14001b0ca  push    r15
0x14001b0cc  lea     rbp, [rsp-80h]
0x14001b0d1  sub     rsp, 180h
0x14001b0d8  mov     rax, cs:__security_cookie
0x14001b0df  xor     rax, rsp
0x14001b0e2  mov     [rbp+0B0h+var_40], rax
0x14001b0e6  mov     rax, [r9+0F0h]
0x14001b0ed  xorps   xmm0, xmm0
0x14001b0f0  mov     r14d, [rbp+0B0h+arg_20]
0x14001b0f7  xor     r11d, r11d
0x14001b0fa  mov     r12, [rbp+0B0h+arg_38]
0x14001b101  mov     edi, r8d
0x14001b104  mov     rbx, [rbp+0B0h+arg_30]
0x14001b10b  mov     r13, r9
0x14001b10e  movzx   r15d, dl
0x14001b112  lea     r8, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\wcifs\\telemetr"...
0x14001b119  movups  [rbp+0B0h+var_110], xmm0
0x14001b11d  mov     r10, [rax+40h]
0x14001b121  movzx   eax, word ptr [r10+20h]
0x14001b126  mov     word ptr [rbp+0B0h+var_110+2], ax
0x14001b12a  mov     word ptr [rbp+0B0h+var_110], ax
0x14001b12e  lea     rax, [r10+22h]
0x14001b132  mov     qword ptr [rbp+0B0h+var_110+8], rax
0x14001b136  lea     rax, WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids
0x14001b13d  test    r14d, r14d
0x14001b140  js      short loc_14001B1A2
0x14001b142  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001b149  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001b150  jz      loc_14001B1F4
0x14001b156  mov     rax, cs:wil_details_featureDescriptors_a
0x14001b15d  cmp     [rax+48h], r11w
0x14001b162  jz      loc_14001B1F4
0x14001b168  mov     [rsp+1B0h+var_148], rbx
0x14001b16d  lea     rax, [rbp+0B0h+var_110]
0x14001b171  mov     [rsp+1B0h+var_150], r12
0x14001b176  mov     [rsp+1B0h+var_158], rax
0x14001b17b  mov     rax, [r9+100h]
0x14001b182  mov     [rsp+1B0h+var_160], edi
0x14001b186  mov     [rsp+1B0h+var_168], rax
0x14001b18b  mov     eax, [r9+0FCh]
0x14001b192  mov     [rsp+1B0h+var_170], eax
0x14001b196  mov     [rsp+1B0h+var_178], rcx
0x14001b19b  call    WPP_RECORDER_SF_sDqLiLZii
0x14001b1a0  jmp     short loc_14001B1EA
0x14001b1a2  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001b1a9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001b1b0  jz      short loc_14001B1F4
0x14001b1b2  mov     [rsp+1B0h+var_170], r14d
0x14001b1b7  mov     r9d, 0Eh
0x14001b1bd  mov     [rsp+1B0h+var_178], rcx
0x14001b1c2  mov     dl, 2
0x14001b1c4  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001b1cb  mov     [rsp+1B0h+var_180], 0FAh
0x14001b1d3  mov     [rsp+1B0h+var_188], r8
0x14001b1d8  lea     r8d, [r9-4]
0x14001b1dc  mov     [rsp+1B0h+var_190], rax
0x14001b1e1  mov     rcx, [rcx+40h]
0x14001b1e5  call    WPP_RECORDER_SF_sDqd
0x14001b1ea  lea     r8, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\wcifs\\telemetr"...
0x14001b1f1  xor     r11d, r11d
0x14001b1f4  sub     edi, 1
0x14001b1f7  jz      loc_14001B33F
0x14001b1fd  cmp     edi, 1
0x14001b200  jnz     loc_14001B4F6
0x14001b206  mov     eax, cs:dword_14000E060
0x14001b20c  cmp     eax, 5
0x14001b20f  jbe     loc_14001B4F6
0x14001b215  mov     rdx, 400000000000h
0x14001b21f  lea     rcx, dword_14000E060
0x14001b226  call    _tlgKeywordOn
0x14001b22b  test    al, al
0x14001b22d  jz      loc_14001B4F6
0x14001b233  lea     rax, [rsp+1B0h+var_140]
0x14001b238  mov     [rsp+1B0h+var_140], r14d
0x14001b23d  mov     [rbp+0B0h+var_D0], rax
0x14001b241  lea     rax, [rsp+1B0h+var_13C]
0x14001b246  mov     [rbp+0B0h+var_C0], rax
0x14001b24a  mov     rax, qword ptr [rbp+0B0h+var_110+8]
0x14001b24e  mov     [rbp+0B0h+var_C8], 4
0x14001b256  mov     [rsp+1B0h+var_13C], r15d
0x14001b25b  mov     [rbp+0B0h+var_B8], 4
0x14001b263  test    rax, rax
0x14001b266  jz      short loc_14001B26E
0x14001b268  movzx   edx, word ptr [rbp+0B0h+var_110]
0x14001b26c  jmp     short loc_14001B278
0x14001b26e  mov     rax, cs:off_14000A5B8
0x14001b275  mov     edx, r11d
0x14001b278  mov     [rbp+0B0h+var_A0], rax
0x14001b27c  lea     r8, [rbp+0B0h+var_98]
0x14001b280  movzx   eax, dx
0x14001b283  lea     rcx, dword_14000E060
0x14001b28a  mov     dword ptr [rbp+0B0h+var_98], eax
0x14001b28d  lea     rdx, unk_14000B898
0x14001b294  mov     eax, [r13+0FCh]
0x14001b29b  xor     r9d, r9d
0x14001b29e  mov     [rsp+1B0h+var_138], eax
0x14001b2a2  lea     rax, [rsp+1B0h+var_138]
0x14001b2a7  mov     [rbp+0B0h+var_90], rax
0x14001b2ab  mov     rax, [r13+100h]
0x14001b2b2  mov     [rbp+0B0h+var_130], rax
0x14001b2b6  lea     rax, [rbp+0B0h+var_130]
0x14001b2ba  mov     [rbp+0B0h+var_80], rax
0x14001b2be  mov     rax, [rbp+0B0h+arg_28]
0x14001b2c5  mov     [rbp+0B0h+var_128], rax
0x14001b2c9  lea     rax, [rbp+0B0h+var_128]
0x14001b2cd  mov     [rbp+0B0h+var_70], rax
0x14001b2d1  lea     rax, [rbp+0B0h+var_120]
0x14001b2d5  mov     [rbp+0B0h+var_60], rax
0x14001b2d9  lea     rax, [rbp+0B0h+var_118]
0x14001b2dd  mov     [rbp+0B0h+var_50], rax
0x14001b2e1  lea     rax, [rbp+0B0h+var_F0]
0x14001b2e5  mov     [rbp+0B0h+var_B0], r8
0x14001b2e9  xor     r8d, r8d
0x14001b2ec  mov     [rsp+1B0h+var_188], rax
0x14001b2f1  mov     dword ptr [rsp+1B0h+var_190], 0Bh
0x14001b2f9  mov     [rbp+0B0h+var_A8], 2
0x14001b301  mov     dword ptr [rbp+0B0h+var_98+4], r11d
0x14001b305  mov     [rbp+0B0h+var_88], 4
0x14001b30d  mov     [rbp+0B0h+var_78], 8
0x14001b315  mov     [rbp+0B0h+var_68], 8
0x14001b31d  mov     [rbp+0B0h+var_120], rbx
0x14001b321  mov     [rbp+0B0h+var_58], 8
0x14001b329  mov     [rbp+0B0h+var_118], r12
0x14001b32d  mov     [rbp+0B0h+var_48], 8
0x14001b335  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001b33a  jmp     loc_14001B4F6
0x14001b33f  test    r14d, r14d
0x14001b342  js      loc_14001B4F6
0x14001b348  test    r15b, r15b
0x14001b34b  jnz     loc_14001B4F6
0x14001b351  mov     r9d, 400h
0x14001b357  mov     edi, 1
0x14001b35c  cmp     rbx, r9
0x14001b35f  jnb     short loc_14001B366
0x14001b361  mov     r9d, edi
0x14001b364  jmp     short loc_14001B38E
0x14001b366  mov     eax, 100000h
0x14001b36b  cmp     rbx, rax
0x14001b36e  jnb     short loc_14001B376
0x14001b370  shr     rbx, 0Ah
0x14001b374  jmp     short loc_14001B38E
0x14001b376  mov     r9d, 40000000h
0x14001b37c  cmp     rbx, r9
0x14001b37f  jnb     short loc_14001B38A
0x14001b381  mov     r9d, eax
0x14001b384  shr     rbx, 14h
0x14001b388  jmp     short loc_14001B38E
0x14001b38a  shr     rbx, 1Eh
0x14001b38e  mov     rax, rbx
0x14001b391  mov     [rbp+0B0h+var_100], r11
0x14001b395  mul     rbx
0x14001b398  mov     r10, rax
0x14001b39b  test    rdx, rdx
0x14001b39e  jnz     loc_14001B4B0
0x14001b3a4  mov     ecx, cs:dword_14000E060
0x14001b3aa  cmp     ecx, 5
0x14001b3ad  jbe     loc_14001B4F6
0x14001b3b3  mov     rdx, 400000000000h
0x14001b3bd  lea     rcx, dword_14000E060
0x14001b3c4  call    _tlgKeywordOn
0x14001b3c9  test    al, al
0x14001b3cb  jz      loc_14001B4F6
0x14001b3d1  lea     rax, [rbp+0B0h+var_118]
0x14001b3d5  mov     [rbp+0B0h+var_118], rdi
0x14001b3d9  mov     [rbp+0B0h+var_D0], rax
0x14001b3dd  lea     rdx, byte_14000B961; int
0x14001b3e4  lea     rax, [rbp+0B0h+var_120]
0x14001b3e8  mov     [rbp+0B0h+var_C8], 8
0x14001b3f0  mov     [rbp+0B0h+var_C0], rax
0x14001b3f4  lea     rax, [rbp+0B0h+var_128]
0x14001b3f8  mov     [rbp+0B0h+var_B0], rax
0x14001b3fc  lea     rax, [rbp+0B0h+var_130]
0x14001b400  mov     [rbp+0B0h+var_A0], rax
0x14001b404  lea     rax, [rbp+0B0h+var_F8]
0x14001b408  mov     [rbp+0B0h+var_90], rax
0x14001b40c  lea     rax, [rsp+1B0h+var_138]
0x14001b411  mov     [rbp+0B0h+var_80], rax
0x14001b415  mov     eax, [rbp+0B0h+arg_40]
0x14001b41b  mov     [rsp+1B0h+var_13C], eax
0x14001b41f  lea     rax, [rsp+1B0h+var_13C]
0x14001b424  mov     [rbp+0B0h+var_70], rax
0x14001b428  mov     eax, [rbp+0B0h+arg_48]
0x14001b42e  mov     [rsp+1B0h+var_140], eax
0x14001b432  lea     rax, [rsp+1B0h+var_140]
0x14001b437  mov     [rbp+0B0h+var_60], rax
0x14001b43b  lea     rax, [rbp+0B0h+var_100]
0x14001b43f  mov     [rbp+0B0h+var_50], rax
0x14001b443  lea     rax, [rbp+0B0h+var_F0]
0x14001b447  mov     [rsp+1B0h+var_190], rax; PEVENT_DATA_DESCRIPTOR
0x14001b44c  mov     [rbp+0B0h+var_120], rbx
0x14001b450  mov     [rbp+0B0h+var_B8], 8
0x14001b458  mov     [rbp+0B0h+var_128], r10
0x14001b45c  mov     [rbp+0B0h+var_A8], 8
0x14001b464  mov     [rbp+0B0h+var_130], rbx
0x14001b468  mov     [rbp+0B0h+var_98], 8
0x14001b470  mov     [rbp+0B0h+var_F8], rbx
0x14001b474  mov     [rbp+0B0h+var_88], 8
0x14001b47c  mov     [rsp+1B0h+var_138], r9d
0x14001b481  mov     [rbp+0B0h+var_78], 4
0x14001b489  mov     [rbp+0B0h+var_68], 4
0x14001b491  mov     [rbp+0B0h+var_58], 4
0x14001b499  mov     [rbp+0B0h+var_100], 1000000h
0x14001b4a1  mov     [rbp+0B0h+var_48], 8
0x14001b4a9  call    _tlgWriteAgg
0x14001b4ae  jmp     short loc_14001B4F6
0x14001b4b0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001b4b7  jz      short loc_14001B4F6
0x14001b4b9  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001b4c0  lea     rax, WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids
0x14001b4c7  mov     dword ptr [rsp+1B0h+var_178], 0C0000095h
0x14001b4cf  mov     r9d, 0Fh
0x14001b4d5  mov     [rsp+1B0h+var_180], 146h
0x14001b4dd  mov     dl, 3
0x14001b4df  mov     [rsp+1B0h+var_188], r8
0x14001b4e4  mov     rcx, [rcx+40h]
0x14001b4e8  lea     r8d, [r9-5]
0x14001b4ec  mov     [rsp+1B0h+var_190], rax
0x14001b4f1  call    WPP_RECORDER_SF_sDd
0x14001b4f6  mov     rcx, [rbp+0B0h+var_40]
0x14001b4fa  xor     rcx, rsp; StackCookie
0x14001b4fd  call    __security_check_cookie
0x14001b502  mov     rbx, [rsp+1B0h+arg_8]
0x14001b50a  add     rsp, 180h
0x14001b511  pop     r15
0x14001b513  pop     r14
0x14001b515  pop     r13
0x14001b517  pop     r12
0x14001b519  pop     rdi
0x14001b51a  pop     rsi
0x14001b51b  pop     rbp
0x14001b51c  retn
```
