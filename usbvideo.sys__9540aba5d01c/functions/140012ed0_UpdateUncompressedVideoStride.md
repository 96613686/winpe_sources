# UpdateUncompressedVideoStride

- ea: `0x140012ed0`
- end: `0x14001312b`
- name: `UpdateUncompressedVideoStride`
- size: `603`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000fa28`
- `0x140011bc0`

## callees

- `0x140004bac`
- `0x140012ed0`
- `0x14003c868`

## pseudocode

```c
__int64 __fastcall UpdateUncompressedVideoStride(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rcx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  int v17; // r10d
  unsigned int v18; // eax
  int v19; // edx
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // eax

  v5 = a3;
  if ( a3 && a4 )
  {
    v6 = *(_QWORD *)(a1 + 96);
    v7 = *(_QWORD *)(v6 + 16) - *(_QWORD *)&KSDATAFORMAT_TYPE_VIDEO.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)(v6 + 24) - *(_QWORD *)KSDATAFORMAT_TYPE_VIDEO.Data4;
    if ( !v7 )
    {
      v8 = *(_QWORD *)(v6 + 32) - *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1;
      if ( !v8 )
        v8 = *(_QWORD *)(v6 + 40) - *(_QWORD *)MEDIASUBTYPE_YUY2.Data4;
      if ( !v8 )
      {
        v9 = *(_QWORD *)&KSDATAFORMAT_TYPE_VIDEO.Data1 - a2[2];
        if ( !v9 )
          v9 = *(_QWORD *)KSDATAFORMAT_TYPE_VIDEO.Data4 - a2[3];
        if ( !v9 )
        {
          v10 = *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 - a2[4];
          if ( !v10 )
            v10 = *(_QWORD *)MEDIASUBTYPE_YUY2.Data4 - a2[5];
          if ( !v10 )
          {
            v11 = -1073741823;
            v12 = *(_QWORD *)(v6 + 48);
            v13 = *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data1 - v12;
            if ( *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data1 == v12 )
              v13 = *(_QWORD *)KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data4 - *(_QWORD *)(v6 + 56);
            if ( !v13 )
            {
              v14 = *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data1 - a2[6];
              if ( !v14 )
                v14 = *(_QWORD *)KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data4 - a2[7];
              if ( !v14 )
              {
                if ( *(_DWORD *)v6 < 0x98u )
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  {
                    return v11;
                  }
                  v16 = 27;
                  goto LABEL_25;
                }
                v17 = v6 + 112;
                v18 = *(_DWORD *)(v6 + 112);
                if ( v18 + 48 >= v18 && v18 + 112 >= v18 + 48 && v18 + 112 <= *(_DWORD *)v6 )
                {
                  v19 = (_DWORD)a2 + 112;
                  return (unsigned int)UpdateUncompressedVideoStrideBitmapHeader(v17, v19, *(_DWORD *)(v6 + 8), v5, a4);
                }
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  return v11;
                v16 = 28;
                goto LABEL_25;
              }
            }
            v20 = *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data1 - v12;
            if ( *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data1 == v12 )
              v20 = *(_QWORD *)KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data4 - *(_QWORD *)(v6 + 56);
            if ( !v20 )
            {
              v21 = *(_QWORD *)&KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data1 - a2[6];
              if ( !v21 )
                v21 = *(_QWORD *)KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data4 - a2[7];
              if ( !v21 )
              {
                if ( *(_DWORD *)v6 >= 0xB0u )
                {
                  v17 = v6 + 136;
                  v22 = *(_DWORD *)(v6 + 136);
                  if ( v22 + 72 >= v22 && v22 + 136 >= v22 + 72 && v22 + 136 <= *(_DWORD *)v6 )
                  {
                    v19 = (_DWORD)a2 + 136;
                    return (unsigned int)UpdateUncompressedVideoStrideBitmapHeader(
                                           v17,
                                           v19,
                                           *(_DWORD *)(v6 + 8),
                                           v5,
                                           a4);
                  }
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  {
                    return v11;
                  }
                  v16 = 30;
                }
                else
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  {
                    return v11;
                  }
                  v16 = 29;
                }
LABEL_25:
                WPP_SF_(v15->AttachedDevice, v16, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids);
                return v11;
              }
            }
          }
        }
      }
    }
    return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140012ed0  mov     [rsp+arg_0], rbx
0x140012ed5  push    rdi
0x140012ed6  sub     rsp, 30h
0x140012eda  mov     r11, r9
0x140012edd  mov     rdi, r8
0x140012ee0  test    r8, r8
0x140012ee3  jz      loc_14001311D
0x140012ee9  test    r9, r9
0x140012eec  jz      loc_14001311D
0x140012ef2  mov     r8, [rcx+60h]
0x140012ef6  mov     r9, qword ptr cs:KSDATAFORMAT_TYPE_VIDEO.Data1
0x140012efd  mov     rcx, [r8+10h]
0x140012f01  sub     rcx, r9
0x140012f04  jnz     short loc_140012F11
0x140012f06  mov     rcx, [r8+18h]
0x140012f0a  sub     rcx, qword ptr cs:KSDATAFORMAT_TYPE_VIDEO.Data4
0x140012f11  test    rcx, rcx
0x140012f14  jnz     loc_140013117
0x140012f1a  mov     rax, [r8+20h]
0x140012f1e  mov     rcx, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x140012f25  mov     r10, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x140012f2c  sub     rax, rcx
0x140012f2f  jnz     short loc_140012F38
0x140012f31  mov     rax, [r8+28h]
0x140012f35  sub     rax, r10
0x140012f38  test    rax, rax
0x140012f3b  jnz     loc_140013117
0x140012f41  sub     r9, [rdx+10h]
0x140012f45  jnz     short loc_140012F52
0x140012f47  mov     r9, qword ptr cs:KSDATAFORMAT_TYPE_VIDEO.Data4
0x140012f4e  sub     r9, [rdx+18h]
0x140012f52  test    r9, r9
0x140012f55  jnz     loc_140013117
0x140012f5b  sub     rcx, [rdx+20h]
0x140012f5f  jnz     short loc_140012F68
0x140012f61  mov     rcx, r10
0x140012f64  sub     rcx, [rdx+28h]
0x140012f68  test    rcx, rcx
0x140012f6b  jnz     loc_140013117
0x140012f71  mov     rcx, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data1
0x140012f78  mov     ebx, 0C0000001h
0x140012f7d  mov     rax, [r8+30h]
0x140012f81  mov     r9, rcx
0x140012f84  sub     r9, rax
0x140012f87  jnz     short loc_140012F94
0x140012f89  mov     r9, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data4
0x140012f90  sub     r9, [r8+38h]
0x140012f94  test    r9, r9
0x140012f97  jnz     loc_140013061
0x140012f9d  sub     rcx, [rdx+30h]
0x140012fa1  jnz     short loc_140012FAE
0x140012fa3  mov     rcx, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO.Data4
0x140012faa  sub     rcx, [rdx+38h]
0x140012fae  test    rcx, rcx
0x140012fb1  jnz     loc_140013061
0x140012fb7  mov     ecx, [r8]
0x140012fba  cmp     ecx, 98h
0x140012fc0  jnb     short loc_140012FFD
0x140012fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fc9  lea     rax, WPP_GLOBAL_Control
0x140012fd0  cmp     rcx, rax
0x140012fd3  jz      loc_140013119
0x140012fd9  cmp     byte ptr [rcx+29h], 3
0x140012fdd  jb      loc_140013119
0x140012fe3  mov     edx, 1Bh
0x140012fe8  mov     rcx, [rcx+18h]
0x140012fec  lea     r8, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids
0x140012ff3  call    WPP_SF_
0x140012ff8  jmp     loc_140013119
0x140012ffd  lea     r10, [r8+70h]
0x140013001  mov     eax, [r10]
0x140013004  lea     r9d, [rax+30h]
0x140013008  cmp     r9d, eax
0x14001300b  jb      short loc_140013039
0x14001300d  lea     eax, [r9+40h]
0x140013011  cmp     eax, r9d
0x140013014  jb      short loc_140013039
0x140013016  cmp     eax, ecx
0x140013018  ja      short loc_140013039
0x14001301a  add     rdx, 70h ; 'p'
0x14001301e  mov     r8d, [r8+8]
0x140013022  mov     r9, rdi
0x140013025  mov     rcx, r10
0x140013028  mov     [rsp+38h+var_18], r11
0x14001302d  call    UpdateUncompressedVideoStrideBitmapHeader
0x140013032  mov     ebx, eax
0x140013034  jmp     loc_140013119
0x140013039  mov     rcx, cs:WPP_GLOBAL_Control
0x140013040  lea     rax, WPP_GLOBAL_Control
0x140013047  cmp     rcx, rax
0x14001304a  jz      loc_140013119
0x140013050  cmp     byte ptr [rcx+29h], 3
0x140013054  jb      loc_140013119
0x14001305a  mov     edx, 1Ch
0x14001305f  jmp     short loc_140012FE8
0x140013061  mov     rcx, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data1
0x140013068  mov     r9, rcx
0x14001306b  sub     r9, rax
0x14001306e  jnz     short loc_14001307B
0x140013070  mov     r9, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data4
0x140013077  sub     r9, [r8+38h]
0x14001307b  test    r9, r9
0x14001307e  jnz     loc_140013117
0x140013084  sub     rcx, [rdx+30h]
0x140013088  jnz     short loc_140013095
0x14001308a  mov     rcx, qword ptr cs:KSDATAFORMAT_SPECIFIER_VIDEOINFO2.Data4
0x140013091  sub     rcx, [rdx+38h]
0x140013095  test    rcx, rcx
0x140013098  jnz     short loc_140013117
0x14001309a  mov     ecx, [r8]
0x14001309d  cmp     ecx, 0B0h
0x1400130a3  jnb     short loc_1400130C8
0x1400130a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130ac  lea     rax, WPP_GLOBAL_Control
0x1400130b3  cmp     rcx, rax
0x1400130b6  jz      short loc_140013119
0x1400130b8  cmp     byte ptr [rcx+29h], 3
0x1400130bc  jb      short loc_140013119
0x1400130be  mov     edx, 1Dh
0x1400130c3  jmp     loc_140012FE8
0x1400130c8  lea     r10, [r8+88h]
0x1400130cf  mov     eax, [r10]
0x1400130d2  lea     r9d, [rax+48h]
0x1400130d6  cmp     r9d, eax
0x1400130d9  jb      short loc_1400130F4
0x1400130db  lea     eax, [r9+40h]
0x1400130df  cmp     eax, r9d
0x1400130e2  jb      short loc_1400130F4
0x1400130e4  cmp     eax, ecx
0x1400130e6  ja      short loc_1400130F4
0x1400130e8  add     rdx, 88h
0x1400130ef  jmp     loc_14001301E
0x1400130f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130fb  lea     rax, WPP_GLOBAL_Control
0x140013102  cmp     rcx, rax
0x140013105  jz      short loc_140013119
0x140013107  cmp     byte ptr [rcx+29h], 3
0x14001310b  jb      short loc_140013119
0x14001310d  mov     edx, 1Eh
0x140013112  jmp     loc_140012FE8
0x140013117  xor     ebx, ebx
0x140013119  mov     eax, ebx
0x14001311b  jmp     short loc_14001311F
0x14001311d  xor     eax, eax
0x14001311f  mov     rbx, [rsp+38h+arg_0]
0x140013124  add     rsp, 30h
0x140013128  pop     rdi
0x140013129  retn
```
