# sub_14000EBFC

- ea: `0x14000ebfc`
- end: `0x14000ef6b`
- name: `sub_14000EBFC`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14000b988`

## callees

- `0x140001008`
- `0x140003c8c`
- `0x14000ebfc`
- `0x140012ef4`
- `0x140012fd8`
- `0x1400138b8`
- `0x1400142c0`
- `0x140015fb8`
- `0x140016176`
- `0x140016a40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14000ec3f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000ec82`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000ec3f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000ec82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef24`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef24`

## pseudocode

```c
__int64 __fastcall sub_14000EBFC(unsigned __int16 *a1, __int64 a2)
{
  unsigned int CurrentProcessId; // eax
  int v5; // r8d
  char v6; // bl
  HANDLE v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rsi
  int v10; // eax
  unsigned int *v11; // rcx
  unsigned int *v12; // rax
  char *v13; // rdx
  int v14; // eax
  PEVENT_DATA_DESCRIPTOR v16[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-C0h] BYREF
  char v18; // [rsp+58h] [rbp-B0h] BYREF
  char v19; // [rsp+59h] [rbp-AFh] BYREF
  unsigned int v20; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v22[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v24; // [rsp+98h] [rbp-70h]
  __int64 v25; // [rsp+A0h] [rbp-68h]
  wchar_t *v26; // [rsp+A8h] [rbp-60h]
  int v27; // [rsp+B0h] [rbp-58h]
  int v28; // [rsp+B4h] [rbp-54h]
  int *v29; // [rsp+B8h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-48h]
  PEVENT_DATA_DESCRIPTOR v31; // [rsp+C8h] [rbp-40h]
  int v32; // [rsp+D0h] [rbp-38h] BYREF
  int v33; // [rsp+D4h] [rbp-34h]
  int *v34; // [rsp+D8h] [rbp-30h]
  __int64 v35; // [rsp+E0h] [rbp-28h]
  __int64 v36; // [rsp+E8h] [rbp-20h]
  int v37; // [rsp+F0h] [rbp-18h] BYREF
  int v38; // [rsp+F4h] [rbp-14h]
  const char *v39; // [rsp+F8h] [rbp-10h]
  __int64 v40; // [rsp+100h] [rbp-8h]
  unsigned int *v41; // [rsp+108h] [rbp+0h]
  __int64 v42; // [rsp+110h] [rbp+8h]
  unsigned int *v43; // [rsp+118h] [rbp+10h]
  __int64 v44; // [rsp+120h] [rbp+18h]
  char *v45; // [rsp+128h] [rbp+20h]
  __int64 v46; // [rsp+130h] [rbp+28h]

  *(_OWORD *)v16 = 0;
  v18 = 0;
  CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
  LOBYTE(v5) = 1;
  v6 = sub_1400138B8(CurrentProcessId, (unsigned int)v16, v5, 7, (__int64)&v18);
  v17 = 0;
  v7 = PsGetCurrentProcessId();
  sub_140012EF4(v7, &v17);
  if ( *((_QWORD *)&v17 + 1) )
  {
    v8 = *(_QWORD *)(a2 + 8);
    if ( !*(_QWORD *)(v8 + 8) )
      goto LABEL_17;
    if ( !*(_WORD *)v8 )
      goto LABEL_17;
    v9 = (wchar_t *)sub_140012FD8(&v17);
    if ( !v9 )
      goto LABEL_17;
    if ( v6 )
    {
      if ( !(unsigned __int8)sub_1400142C0(1)
        || (unsigned int)dword_140021000 <= 5
        || (qword_140021010 & 0x400000000000LL) == 0
        || (qword_140021018 & 0x400000000000LL) != qword_140021018 )
      {
        goto LABEL_16;
      }
      v22[0] = 0x1000000;
      v24 = v22;
      v25 = 8;
      v10 = wcslen(v9);
      v26 = v9;
      v28 = 0;
      v30 = 2;
      v33 = 0;
      v27 = 2 * v10 + 2;
      v29 = &v32;
      v31 = v16[1];
      v32 = LOWORD(v16[0]);
      v34 = &v37;
      v36 = *((_QWORD *)a1 + 1);
      v37 = *a1;
      v39 = "4.6.0.0";
      v35 = 2;
      v38 = 0;
      v40 = 8;
      v20 = sub_140003C8C();
      v11 = (unsigned int *)&v21;
      v12 = &v20;
      LODWORD(v21) = v6 == 0 ? 0xC0000022 : 0;
      v13 = byte_14001F095;
    }
    else
    {
      if ( (unsigned int)dword_140021000 <= 5
        || (qword_140021010 & 0x800000000000LL) == 0
        || (qword_140021018 & 0x800000000000LL) != qword_140021018 )
      {
        goto LABEL_16;
      }
      v22[0] = 0x1000000;
      v24 = v22;
      v25 = 8;
      v14 = wcslen(v9);
      v26 = v9;
      v28 = 0;
      v30 = 2;
      v33 = 0;
      v27 = 2 * v14 + 2;
      v29 = &v32;
      v31 = v16[1];
      v32 = LOWORD(v16[0]);
      v34 = &v37;
      v36 = *((_QWORD *)a1 + 1);
      v37 = *a1;
      v39 = "4.6.0.0";
      v35 = 2;
      v38 = 0;
      v40 = 8;
      LODWORD(v21) = sub_140003C8C();
      v11 = &v20;
      v12 = (unsigned int *)&v21;
      v20 = v6 == 0 ? 0xC0000022 : 0;
      v13 = (char *)&byte_14001F11F;
    }
    v41 = v12;
    v19 = v18;
    v45 = &v19;
    v43 = v11;
    v42 = 4;
    v44 = 4;
    v46 = 1;
    sub_140001008((int)&dword_140021000, (int)v13, 0, 0, 0xCu, &v23);
LABEL_16:
    ExFreePoolWithTag(v9, 0);
LABEL_17:
    ExFreePoolWithTag(*((PVOID *)&v17 + 1), 0);
  }
  if ( v16[1] )
    sub_140015FB8();
  return v6 == 0 ? 0xC0000022 : 0;
}

```

## disassembly

```asm
0x14000ebfc  mov     rax, rsp
0x14000ebff  mov     [rax+8], rbx
0x14000ec03  mov     [rax+10h], rsi
0x14000ec07  mov     [rax+18h], rdi
0x14000ec0b  push    rbp
0x14000ec0c  push    r12
0x14000ec0e  push    r15
0x14000ec10  lea     rbp, [rax-58h]
0x14000ec14  sub     rsp, 140h
0x14000ec1b  mov     rax, cs:__security_cookie
0x14000ec22  xor     rax, rsp
0x14000ec25  mov     [rbp+50h+var_20], rax
0x14000ec29  xorps   xmm0, xmm0
0x14000ec2c  xor     r12d, r12d
0x14000ec2f  movups  xmmword ptr [rsp+150h+var_128+8], xmm0
0x14000ec34  mov     byte ptr [rsp+150h+var_100], r12b
0x14000ec39  mov     rsi, rdx
0x14000ec3c  mov     r15, rcx
0x14000ec3f  call    cs:PsGetCurrentProcessId
0x14000ec46  nop     dword ptr [rax+rax+00h]
0x14000ec4b  lea     r9d, [r12+7]
0x14000ec50  mov     r8b, 1
0x14000ec53  mov     rcx, rax
0x14000ec56  lea     rdx, [rsp+150h+var_128+8]
0x14000ec5b  lea     rax, [rsp+150h+var_100]
0x14000ec60  mov     qword ptr [rsp+150h+var_130], rax
0x14000ec65  call    sub_1400138B8
0x14000ec6a  mov     cl, al
0x14000ec6c  xorps   xmm0, xmm0
0x14000ec6f  neg     cl
0x14000ec71  mov     bl, al
0x14000ec73  movups  [rsp+150h+var_118+8], xmm0
0x14000ec78  sbb     edi, edi
0x14000ec7a  not     edi
0x14000ec7c  and     edi, 0C0000022h
0x14000ec82  call    cs:PsGetCurrentProcessId
0x14000ec89  nop     dword ptr [rax+rax+00h]
0x14000ec8e  mov     rcx, rax
0x14000ec91  lea     rdx, [rsp+150h+var_118+8]
0x14000ec96  call    sub_140012EF4
0x14000ec9b  cmp     [rsp+150h+P], r12
0x14000eca0  jz      loc_14000EF30
0x14000eca6  mov     rax, [rsi+8]
0x14000ecaa  cmp     [rax+8], r12
0x14000ecae  jz      loc_14000EF1D
0x14000ecb4  cmp     [rax], r12w
0x14000ecb8  jbe     loc_14000EF1D
0x14000ecbe  lea     rcx, [rsp+150h+var_118+8]
0x14000ecc3  call    sub_140012FD8
0x14000ecc8  mov     rsi, rax
0x14000eccb  test    rax, rax
0x14000ecce  jz      loc_14000EF1D
0x14000ecd4  test    bl, bl
0x14000ecd6  jz      loc_14000EDD7
0x14000ecdc  lea     ecx, [r12+1]
0x14000ece1  call    sub_1400142C0
0x14000ece6  test    al, al
0x14000ece8  jz      loc_14000EF0C
0x14000ecee  mov     rbx, cs:off_140019010
0x14000ecf5  cmp     dword ptr [rbx], 5
0x14000ecf8  jbe     loc_14000EF0C
0x14000ecfe  mov     rdx, 400000000000h
0x14000ed08  test    [rbx+10h], rdx
0x14000ed0c  jz      loc_14000EF0C
0x14000ed12  mov     rcx, [rbx+18h]
0x14000ed16  mov     rax, rcx
0x14000ed19  and     rax, rdx
0x14000ed1c  cmp     rax, rcx
0x14000ed1f  jnz     loc_14000EF0C
0x14000ed25  lea     rax, [rsp+150h+var_F0]
0x14000ed2a  mov     [rsp+150h+var_F0], 1000000h
0x14000ed33  mov     rcx, rsi; Str
0x14000ed36  mov     [rbp+50h+var_C0], rax
0x14000ed3a  mov     [rbp+50h+var_B8], 8
0x14000ed42  call    wcslen
0x14000ed47  mov     [rbp+50h+var_B0], rsi
0x14000ed4b  mov     [rbp+50h+var_A4], r12d
0x14000ed4f  mov     [rbp+50h+var_98], 2
0x14000ed57  lea     eax, ds:2[rax*2]
0x14000ed5e  mov     [rbp+50h+var_84], r12d
0x14000ed62  mov     [rbp+50h+var_A8], eax
0x14000ed65  lea     rax, [rbp+50h+var_88]
0x14000ed69  mov     [rbp+50h+var_A0], rax
0x14000ed6d  mov     rax, qword ptr [rsp+150h+var_118]
0x14000ed72  mov     [rbp+50h+var_90], rax
0x14000ed76  movzx   eax, word ptr [rsp+150h+var_128+8]
0x14000ed7b  mov     [rbp+50h+var_88], eax
0x14000ed7e  lea     rax, [rbp+50h+var_68]
0x14000ed82  mov     [rbp+50h+var_80], rax
0x14000ed86  mov     rax, [r15+8]
0x14000ed8a  mov     [rbp+50h+var_70], rax
0x14000ed8e  movzx   eax, word ptr [r15]
0x14000ed92  mov     [rbp+50h+var_68], eax
0x14000ed95  lea     rax, a4600; "4.6.0.0"
0x14000ed9c  mov     [rbp+50h+var_60], rax
0x14000eda0  mov     [rbp+50h+var_78], 2
0x14000eda8  mov     [rbp+50h+var_64], r12d
0x14000edac  mov     [rbp+50h+var_58], 8
0x14000edb4  call    sub_140003C8C
0x14000edb9  mov     [rsp+150h+var_FC], eax
0x14000edbd  lea     rcx, [rsp+150h+var_F8]
0x14000edc2  lea     rax, [rsp+150h+var_FC]
0x14000edc7  mov     dword ptr [rsp+150h+var_F8], edi
0x14000edcb  lea     rdx, byte_14001F095
0x14000edd2  jmp     loc_14000EEBB
0x14000edd7  mov     rbx, cs:off_140019010
0x14000edde  cmp     dword ptr [rbx], 5
0x14000ede1  jbe     loc_14000EF0C
0x14000ede7  mov     rdx, 800000000000h
0x14000edf1  test    [rbx+10h], rdx
0x14000edf5  jz      loc_14000EF0C
0x14000edfb  mov     rcx, [rbx+18h]
0x14000edff  mov     rax, rcx
0x14000ee02  and     rax, rdx
0x14000ee05  cmp     rax, rcx
0x14000ee08  jnz     loc_14000EF0C
0x14000ee0e  lea     rax, [rsp+150h+var_F0]
0x14000ee13  mov     [rsp+150h+var_F0], 1000000h
0x14000ee1c  mov     rcx, rsi; Str
0x14000ee1f  mov     [rbp+50h+var_C0], rax
0x14000ee23  mov     [rbp+50h+var_B8], 8
0x14000ee2b  call    wcslen
0x14000ee30  mov     [rbp+50h+var_B0], rsi
0x14000ee34  mov     [rbp+50h+var_A4], r12d
0x14000ee38  mov     [rbp+50h+var_98], 2
0x14000ee40  lea     eax, ds:2[rax*2]
0x14000ee47  mov     [rbp+50h+var_84], r12d
0x14000ee4b  mov     [rbp+50h+var_A8], eax
0x14000ee4e  lea     rax, [rbp+50h+var_88]
0x14000ee52  mov     [rbp+50h+var_A0], rax
0x14000ee56  mov     rax, qword ptr [rsp+150h+var_118]
0x14000ee5b  mov     [rbp+50h+var_90], rax
0x14000ee5f  movzx   eax, word ptr [rsp+150h+var_128+8]
0x14000ee64  mov     [rbp+50h+var_88], eax
0x14000ee67  lea     rax, [rbp+50h+var_68]
0x14000ee6b  mov     [rbp+50h+var_80], rax
0x14000ee6f  mov     rax, [r15+8]
0x14000ee73  mov     [rbp+50h+var_70], rax
0x14000ee77  movzx   eax, word ptr [r15]
0x14000ee7b  mov     [rbp+50h+var_68], eax
0x14000ee7e  lea     rax, a4600; "4.6.0.0"
0x14000ee85  mov     [rbp+50h+var_60], rax
0x14000ee89  mov     [rbp+50h+var_78], 2
0x14000ee91  mov     [rbp+50h+var_64], r12d
0x14000ee95  mov     [rbp+50h+var_58], 8
0x14000ee9d  call    sub_140003C8C
0x14000eea2  mov     dword ptr [rsp+150h+var_F8], eax
0x14000eea6  lea     rcx, [rsp+150h+var_FC]
0x14000eeab  lea     rax, [rsp+150h+var_F8]
0x14000eeb0  mov     [rsp+150h+var_FC], edi
0x14000eeb4  lea     rdx, byte_14001F11F; int
0x14000eebb  mov     [rbp+50h+var_50], rax
0x14000eebf  xor     r9d, r9d; int
0x14000eec2  mov     al, byte ptr [rsp+150h+var_100]
0x14000eec6  xor     r8d, r8d; int
0x14000eec9  mov     byte ptr [rsp+150h+var_100+1], al
0x14000eecd  lea     rax, [rsp+150h+var_100+1]
0x14000eed2  mov     [rbp+50h+var_30], rax
0x14000eed6  lea     rax, [rsp+150h+var_E0]
0x14000eedb  mov     [rbp+50h+var_40], rcx
0x14000eedf  mov     rcx, rbx; int
0x14000eee2  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x14000eee7  mov     [rsp+150h+var_130], 0Ch; ULONG
0x14000eeef  mov     [rbp+50h+var_48], 4
0x14000eef7  mov     [rbp+50h+var_38], 4
0x14000eeff  mov     [rbp+50h+var_28], 1
0x14000ef07  call    sub_140001008
0x14000ef0c  xor     edx, edx; Tag
0x14000ef0e  mov     rcx, rsi; P
0x14000ef11  call    cs:ExFreePoolWithTag
0x14000ef18  nop     dword ptr [rax+rax+00h]
0x14000ef1d  mov     rcx, [rsp+150h+P]; P
0x14000ef22  xor     edx, edx; Tag
0x14000ef24  call    cs:ExFreePoolWithTag
0x14000ef2b  nop     dword ptr [rax+rax+00h]
0x14000ef30  mov     rcx, qword ptr [rsp+150h+var_118]
0x14000ef35  test    rcx, rcx
0x14000ef38  jz      short loc_14000EF3F
0x14000ef3a  call    sub_140015FB8
0x14000ef3f  mov     eax, edi
0x14000ef41  mov     rcx, [rbp+50h+var_20]
0x14000ef45  xor     rcx, rsp; StackCookie
0x14000ef48  call    __security_check_cookie
0x14000ef4d  lea     r11, [rsp+150h+var_10]
0x14000ef55  mov     rbx, [r11+20h]
0x14000ef59  mov     rsi, [r11+28h]
0x14000ef5d  mov     rdi, [r11+30h]
0x14000ef61  mov     rsp, r11
0x14000ef64  pop     r15
0x14000ef66  pop     r12
0x14000ef68  pop     rbp
0x14000ef69  retn
```
