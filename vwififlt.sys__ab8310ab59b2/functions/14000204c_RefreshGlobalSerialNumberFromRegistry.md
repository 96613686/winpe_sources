# RefreshGlobalSerialNumberFromRegistry

- ea: `0x14000204c`
- end: `0x140002286`
- name: `RefreshGlobalSerialNumberFromRegistry`
- size: `570`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140004d70`
- `0x14000cdd8`

## callees

- `0x14000204c`
- `0x140003634`
- `0x14000ada8`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000db50`
- `0x14000dd6c`

## pseudocode

```c
__int64 __fastcall RefreshGlobalSerialNumberFromRegistry(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // r8
  unsigned int v3; // edi
  char v4; // si
  __int64 v5; // r8
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 Timer_high; // rdx
  int v13; // [rsp+50h] [rbp+8h] BYREF
  int v14; // [rsp+54h] [rbp+Ch]
  int v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = HIDWORD(a1);
  v1 = 10;
  v13 = -1;
  v15 = 10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( (unsigned int)filterReadLong(0, L"GlobalSerialNoEx", &v15) )
  {
    v3 = 10;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_13:
    v4 = 1;
    goto LABEL_17;
  }
  v3 = v15;
  if ( v15 < 10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, v2, (unsigned int)v15, 10);
    v3 = 10;
    goto LABEL_13;
  }
  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_17:
  if ( (unsigned int)filterReadLong(0, L"GlobalSerialNo", &v13) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v7 = 14;
LABEL_21:
      WPP_SF_d(v6->AttachedDevice, v7, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v1 = v13;
      v7 = 15;
      goto LABEL_21;
    }
    v1 = v13;
  }
  if ( (int)v3 >= v1 )
  {
    v8 = 0;
    if ( !v4 )
      goto LABEL_39;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 16, v5, v3, v1 + 1);
    v3 = v1 + 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v9 = filterWriteLong(0, L"GlobalSerialNoEx", v3);
  v8 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 1) != 0 )
        WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v10, v3, v9);
    }
  }
LABEL_39:
  g_ulSerialNo = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x14000204c  mov     rax, rsp
0x14000204f  mov     [rax+18h], rbx
0x140002053  mov     [rax+20h], rbp
0x140002057  mov     [rax+8], rcx
0x14000205b  push    rsi
0x14000205c  push    rdi
0x14000205d  push    r15
0x14000205f  sub     rsp, 30h
0x140002063  mov     ebx, 0Ah
0x140002068  mov     dword ptr [rax+8], 0FFFFFFFFh
0x14000206f  mov     [rax+10h], ebx
0x140002072  mov     rcx, cs:WPP_GLOBAL_Control
0x140002079  lea     rbp, WPP_GLOBAL_Control
0x140002080  lea     r15, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002087  cmp     rcx, rbp
0x14000208a  jz      short loc_1400020A1
0x14000208c  mov     eax, [rcx+2Ch]
0x14000208f  test    al, 20h
0x140002091  jz      short loc_1400020A1
0x140002093  mov     rcx, [rcx+18h]
0x140002097  mov     edx, ebx
0x140002099  mov     r8, r15
0x14000209c  call    WPP_SF_
0x1400020a1  lea     r8, [rsp+48h+arg_8]
0x1400020a6  xor     ecx, ecx
0x1400020a8  lea     rdx, aGlobalserialno_0; "GlobalSerialNoEx"
0x1400020af  call    filterReadLong
0x1400020b4  test    eax, eax
0x1400020b6  jz      short loc_1400020E3
0x1400020b8  mov     edi, ebx
0x1400020ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020c1  cmp     rcx, rbp
0x1400020c4  jz      short loc_140002115
0x1400020c6  mov     eax, [rcx+2Ch]
0x1400020c9  test    al, 4
0x1400020cb  jz      short loc_140002115
0x1400020cd  mov     rcx, [rcx+18h]
0x1400020d1  mov     edx, 0Bh
0x1400020d6  mov     r9d, ebx
0x1400020d9  mov     r8, r15
0x1400020dc  call    WPP_SF_d
0x1400020e1  jmp     short loc_140002115
0x1400020e3  mov     edi, [rsp+48h+arg_8]
0x1400020e7  cmp     edi, ebx
0x1400020e9  jge     short loc_14000211A
0x1400020eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020f2  cmp     rcx, rbp
0x1400020f5  jz      short loc_140002113
0x1400020f7  mov     eax, [rcx+2Ch]
0x1400020fa  test    al, 1
0x1400020fc  jz      short loc_140002113
0x1400020fe  mov     rcx, [rcx+18h]
0x140002102  mov     edx, 0Ch
0x140002107  mov     r9d, edi
0x14000210a  mov     [rsp+48h+var_28], ebx
0x14000210e  call    WPP_SF_Dd
0x140002113  mov     edi, ebx
0x140002115  mov     sil, 1
0x140002118  jmp     short loc_140002144
0x14000211a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002121  xor     sil, sil
0x140002124  cmp     rcx, rbp
0x140002127  jz      short loc_140002144
0x140002129  mov     eax, [rcx+2Ch]
0x14000212c  test    al, 4
0x14000212e  jz      short loc_140002144
0x140002130  mov     rcx, [rcx+18h]
0x140002134  mov     edx, 0Dh
0x140002139  mov     r9d, edi
0x14000213c  mov     r8, r15
0x14000213f  call    WPP_SF_d
0x140002144  lea     r8, [rsp+48h+arg_0]
0x140002149  xor     ecx, ecx
0x14000214b  lea     rdx, aGlobalserialno; "GlobalSerialNo"
0x140002152  call    filterReadLong
0x140002157  test    eax, eax
0x140002159  jz      short loc_140002184
0x14000215b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002162  cmp     rcx, rbp
0x140002165  jz      short loc_1400021A6
0x140002167  mov     eax, [rcx+2Ch]
0x14000216a  test    al, 4
0x14000216c  jz      short loc_1400021A6
0x14000216e  mov     edx, 0Eh
0x140002173  mov     rcx, [rcx+18h]
0x140002177  mov     r9d, ebx
0x14000217a  mov     r8, r15
0x14000217d  call    WPP_SF_d
0x140002182  jmp     short loc_1400021A6
0x140002184  mov     rcx, cs:WPP_GLOBAL_Control
0x14000218b  cmp     rcx, rbp
0x14000218e  jz      short loc_1400021A2
0x140002190  mov     eax, [rcx+2Ch]
0x140002193  test    al, 4
0x140002195  jz      short loc_1400021A2
0x140002197  mov     ebx, [rsp+48h+arg_0]
0x14000219b  mov     edx, 0Fh
0x1400021a0  jmp     short loc_140002173
0x1400021a2  mov     ebx, [rsp+48h+arg_0]
0x1400021a6  cmp     edi, ebx
0x1400021a8  jge     short loc_1400021DA
0x1400021aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021b1  cmp     rcx, rbp
0x1400021b4  jz      short loc_1400021D5
0x1400021b6  mov     eax, [rcx+2Ch]
0x1400021b9  test    al, 4
0x1400021bb  jz      short loc_1400021D5
0x1400021bd  mov     rcx, [rcx+18h]
0x1400021c1  lea     eax, [rbx+1]
0x1400021c4  mov     edx, 10h
0x1400021c9  mov     [rsp+48h+var_28], eax
0x1400021cd  mov     r9d, edi
0x1400021d0  call    WPP_SF_Dd
0x1400021d5  lea     edi, [rbx+1]
0x1400021d8  jmp     short loc_1400021E1
0x1400021da  xor     ebx, ebx
0x1400021dc  test    sil, sil
0x1400021df  jz      short loc_140002243
0x1400021e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021e8  cmp     rcx, rbp
0x1400021eb  jz      short loc_140002208
0x1400021ed  mov     eax, [rcx+2Ch]
0x1400021f0  test    al, 4
0x1400021f2  jz      short loc_140002208
0x1400021f4  mov     rcx, [rcx+18h]
0x1400021f8  mov     edx, 11h
0x1400021fd  mov     r9d, edi
0x140002200  mov     r8, r15
0x140002203  call    WPP_SF_d
0x140002208  mov     r8d, edi
0x14000220b  lea     rdx, aGlobalserialno_0; "GlobalSerialNoEx"
0x140002212  xor     ecx, ecx
0x140002214  call    filterWriteLong
0x140002219  mov     ebx, eax
0x14000221b  test    eax, eax
0x14000221d  jz      short loc_140002243
0x14000221f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002226  cmp     rcx, rbp
0x140002229  jz      short loc_140002243
0x14000222b  mov     edx, [rcx+2Ch]
0x14000222e  test    dl, 1
0x140002231  jz      short loc_140002243
0x140002233  mov     rcx, [rcx+18h]
0x140002237  mov     r9d, edi
0x14000223a  mov     [rsp+48h+var_28], eax
0x14000223e  call    WPP_SF_dD
0x140002243  mov     cs:g_ulSerialNo, edi
0x140002249  mov     rcx, cs:WPP_GLOBAL_Control
0x140002250  cmp     rcx, rbp
0x140002253  jz      short loc_140002270
0x140002255  mov     eax, [rcx+2Ch]
0x140002258  test    al, 20h
0x14000225a  jz      short loc_140002270
0x14000225c  mov     rcx, [rcx+18h]
0x140002260  mov     edx, 13h
0x140002265  mov     r9d, ebx
0x140002268  mov     r8, r15
0x14000226b  call    WPP_SF_d
0x140002270  mov     rbp, [rsp+48h+arg_18]
0x140002275  mov     eax, ebx
0x140002277  mov     rbx, [rsp+48h+arg_10]
0x14000227c  add     rsp, 30h
0x140002280  pop     r15
0x140002282  pop     rdi
0x140002283  pop     rsi
0x140002284  retn
```
