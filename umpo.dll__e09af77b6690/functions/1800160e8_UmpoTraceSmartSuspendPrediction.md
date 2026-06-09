# UmpoTraceSmartSuspendPrediction

- ea: `0x1800160e8`
- end: `0x1800163eb`
- name: `UmpoTraceSmartSuspendPrediction`
- size: `771`
- prototype: `char(int, int, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180017868`

## callees

- `0x18000c04c`
- `0x18000d6cc`
- `0x180010070`
- `0x1800160e8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180016221`
- `ntdll!EtwEventWrite` at `0x180016221`

## pseudocode

```c
char UmpoTraceSmartSuspendPrediction(int a1, int a2, ...)
{
  char result; // al
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  char v6; // [rsp+38h] [rbp-D0h] BYREF
  char v7; // [rsp+39h] [rbp-CFh] BYREF
  char v8; // [rsp+3Ah] [rbp-CEh] BYREF
  char v9; // [rsp+3Bh] [rbp-CDh] BYREF
  int v10; // [rsp+3Ch] [rbp-CCh] BYREF
  int v11; // [rsp+40h] [rbp-C8h] BYREF
  int v12; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v13; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v15[24]; // [rsp+58h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+118h] [rbp+10h] BYREF
  int *v17; // [rsp+138h] [rbp+30h]
  __int64 v18; // [rsp+140h] [rbp+38h]
  int *v19; // [rsp+148h] [rbp+40h]
  __int64 v20; // [rsp+150h] [rbp+48h]
  va_list v21; // [rsp+158h] [rbp+50h]
  __int64 v22; // [rsp+160h] [rbp+58h]
  va_list v23; // [rsp+168h] [rbp+60h]
  __int64 v24; // [rsp+170h] [rbp+68h]
  va_list v25; // [rsp+178h] [rbp+70h]
  __int64 v26; // [rsp+180h] [rbp+78h]
  va_list v27; // [rsp+188h] [rbp+80h]
  __int64 v28; // [rsp+190h] [rbp+88h]
  int *v29; // [rsp+198h] [rbp+90h]
  __int64 v30; // [rsp+1A0h] [rbp+98h]
  __int64 *v31; // [rsp+1A8h] [rbp+A0h]
  __int64 v32; // [rsp+1B0h] [rbp+A8h]
  char *v33; // [rsp+1B8h] [rbp+B0h]
  __int64 v34; // [rsp+1C0h] [rbp+B8h]
  char *v35; // [rsp+1C8h] [rbp+C0h]
  __int64 v36; // [rsp+1D0h] [rbp+C8h]
  char *v37; // [rsp+1D8h] [rbp+D0h]
  __int64 v38; // [rsp+1E0h] [rbp+D8h]
  char *v39; // [rsp+1E8h] [rbp+E0h]
  __int64 v40; // [rsp+1F0h] [rbp+E8h]
  __int64 *v41; // [rsp+1F8h] [rbp+F0h]
  __int64 v42; // [rsp+200h] [rbp+F8h]
  int v43; // [rsp+248h] [rbp+140h] BYREF
  int v44; // [rsp+250h] [rbp+148h] BYREF
  __int64 v45; // [rsp+258h] [rbp+150h] BYREF
  va_list va; // [rsp+258h] [rbp+150h]
  __int64 v47; // [rsp+260h] [rbp+158h] BYREF
  va_list va1; // [rsp+260h] [rbp+158h]
  __int64 v49; // [rsp+268h] [rbp+160h] BYREF
  va_list va2; // [rsp+268h] [rbp+160h]
  __int64 v51; // [rsp+270h] [rbp+168h] BYREF
  va_list va3; // [rsp+270h] [rbp+168h]
  __int64 v53; // [rsp+278h] [rbp+170h] BYREF
  va_list va4; // [rsp+278h] [rbp+170h]
  __int64 v55; // [rsp+280h] [rbp+178h] BYREF
  va_list va5; // [rsp+280h] [rbp+178h]
  __int64 v57; // [rsp+288h] [rbp+180h] BYREF
  va_list va6; // [rsp+288h] [rbp+180h]
  __int64 v59; // [rsp+290h] [rbp+188h] BYREF
  va_list va7; // [rsp+290h] [rbp+188h]
  __int64 v61; // [rsp+298h] [rbp+190h] BYREF
  va_list va8; // [rsp+298h] [rbp+190h]
  __int64 v63; // [rsp+2A0h] [rbp+198h] BYREF
  va_list va9; // [rsp+2A0h] [rbp+198h]
  va_list va10; // [rsp+2A8h] [rbp+1A0h] BYREF

  va_start(va10, a2);
  va_start(va9, a2);
  va_start(va8, a2);
  va_start(va7, a2);
  va_start(va6, a2);
  va_start(va5, a2);
  va_start(va4, a2);
  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v45 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v47 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v49 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v51 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v53 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v55 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v57 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v59 = va_arg(va8, _QWORD);
  va_copy(va9, va8);
  v61 = va_arg(va9, _QWORD);
  va_copy(va10, va9);
  v63 = va_arg(va10, _QWORD);
  v44 = a2;
  v43 = a1;
  v15[0] = &v43;
  v15[1] = 4;
  v15[2] = &v44;
  v15[3] = 4;
  va_copy((va_list)&v15[4], va);
  v15[5] = 8;
  va_copy((va_list)&v15[6], va1);
  va_copy((va_list)&v15[8], va2);
  va_copy((va_list)&v15[10], va3);
  va_copy((va_list)&v15[12], va4);
  va_copy((va_list)&v15[14], va5);
  va_copy((va_list)&v15[16], va6);
  va_copy((va_list)&v15[18], va7);
  va_copy((va_list)&v15[20], va8);
  va_copy((va_list)&v15[22], va9);
  v15[7] = 8;
  v15[9] = 8;
  v15[11] = 8;
  v15[13] = 4;
  v15[15] = 4;
  v15[17] = 1;
  v15[19] = 1;
  v15[21] = 1;
  v15[23] = 1;
  EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_SUSPEND_PREDICTION, 12, v15);
  result = dword_180024190;
  if ( (unsigned int)dword_180024190 > 5 )
  {
    result = tlgKeywordOn();
    if ( result )
    {
      v10 = v43;
      v17 = &v10;
      v11 = v44;
      v19 = &v11;
      va_copy(v21, va);
      va_copy(v23, va1);
      va_copy(v25, va2);
      va_copy(v27, va3);
      v12 = v53;
      v29 = &v12;
      LODWORD(v13) = v55;
      v31 = &v13;
      v6 = v57;
      v33 = &v6;
      v7 = v59;
      v35 = &v7;
      v8 = v61;
      v37 = &v8;
      v9 = v63;
      v39 = &v9;
      v41 = &v14;
      v18 = 4;
      v20 = 4;
      v22 = 8;
      v24 = 8;
      v26 = 8;
      v28 = 8;
      v30 = 4;
      v32 = 4;
      v34 = 1;
      v36 = 1;
      v38 = 1;
      v40 = 1;
      v14 = 0x1000000;
      v42 = 8;
      return tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)&byte_18001F751, v4, v5, 0xFu, &v16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800160e8  mov     rax, rsp
0x1800160eb  mov     [rax+20h], r9
0x1800160ef  mov     [rax+18h], r8
0x1800160f3  mov     [rax+10h], edx
0x1800160f6  mov     [rax+8], ecx
0x1800160f9  push    rbp
0x1800160fa  push    rbx
0x1800160fb  push    rsi
0x1800160fc  push    rdi
0x1800160fd  push    r14
0x1800160ff  lea     rbp, [rax-138h]
0x180016106  sub     rsp, 210h
0x18001610d  mov     rax, cs:__security_cookie
0x180016114  xor     rax, rsp
0x180016117  mov     [rbp+130h+var_30], rax
0x18001611e  mov     rcx, cs:UmpoProviderHandle
0x180016125  lea     rax, [rbp+130h+arg_0]
0x18001612c  mov     [rsp+230h+var_1E0], rax
0x180016131  lea     r9, [rsp+230h+var_1E0]
0x180016136  lea     rax, [rbp+130h+arg_8]
0x18001613d  mov     [rsp+230h+var_1D8], 4
0x180016146  mov     [rsp+230h+var_1D0], rax
0x18001614b  lea     rdx, UMPO_EVT_SMART_SUSPEND_PREDICTION
0x180016152  lea     rax, [rbp+130h+arg_10]
0x180016159  mov     [rsp+230h+var_1C8], 4
0x180016162  mov     [rsp+230h+var_1C0], rax
0x180016167  mov     r8d, 0Ch
0x18001616d  lea     rax, [rbp+130h+arg_18]
0x180016174  mov     qword ptr [rsp+78h], 8
0x18001617d  mov     [rbp+130h+var_1B0], rax
0x180016181  lea     rax, [rbp+130h+arg_20]
0x180016188  mov     [rbp+130h+var_1A0], rax
0x18001618c  lea     rax, [rbp+130h+arg_28]
0x180016193  mov     [rbp+130h+var_190], rax
0x180016197  lea     rax, [rbp+130h+arg_30]
0x18001619e  mov     [rbp+130h+var_180], rax
0x1800161a2  lea     rax, [rbp+130h+arg_38]
0x1800161a9  mov     [rbp+130h+var_170], rax
0x1800161ad  lea     rax, [rbp+130h+arg_40]
0x1800161b4  mov     [rbp+130h+var_160], rax
0x1800161b8  lea     rax, [rbp+130h+arg_48]
0x1800161bf  mov     [rbp+130h+var_150], rax
0x1800161c3  lea     rax, [rbp+130h+arg_50]
0x1800161ca  mov     [rbp+130h+var_140], rax
0x1800161ce  lea     rax, [rbp+130h+arg_58]
0x1800161d5  mov     [rbp+130h+var_130], rax
0x1800161d9  mov     [rbp+130h+var_1A8], 8
0x1800161e1  mov     [rbp+130h+var_198], 8
0x1800161e9  mov     [rbp+130h+var_188], 8
0x1800161f1  mov     [rbp+130h+var_178], 4
0x1800161f9  mov     [rbp+130h+var_168], 4
0x180016201  mov     [rbp+130h+var_158], 1
0x180016209  mov     [rbp+130h+var_148], 1
0x180016211  mov     [rbp+130h+var_138], 1
0x180016219  mov     [rbp+130h+var_128], 1
0x180016221  call    cs:__imp_EtwEventWrite
0x180016227  mov     eax, cs:dword_180024190
0x18001622d  cmp     eax, 5
0x180016230  jbe     loc_1800163CE
0x180016236  call    _tlgKeywordOn
0x18001623b  test    al, al
0x18001623d  jz      loc_1800163CE
0x180016243  mov     eax, [rbp+130h+arg_0]
0x180016249  lea     rdx, byte_18001F751; int
0x180016250  mov     [rsp+230h+var_1FC], eax
0x180016254  lea     rax, [rsp+230h+var_1FC]
0x180016259  mov     [rbp+130h+var_100], rax
0x18001625d  mov     eax, [rbp+130h+arg_8]
0x180016263  mov     [rsp+230h+var_1F8], eax
0x180016267  lea     rax, [rsp+230h+var_1F8]
0x18001626c  mov     [rbp+130h+var_F0], rax
0x180016270  lea     rax, [rbp+130h+arg_10]
0x180016277  mov     [rbp+130h+var_E0], rax
0x18001627b  lea     rax, [rbp+130h+arg_18]
0x180016282  mov     [rbp+130h+var_D0], rax
0x180016286  lea     rax, [rbp+130h+arg_20]
0x18001628d  mov     [rbp+130h+var_C0], rax
0x180016291  lea     rax, [rbp+130h+arg_28]
0x180016298  mov     [rbp+130h+var_B0], rax
0x18001629f  mov     eax, dword ptr [rbp+130h+arg_30]
0x1800162a5  mov     [rsp+230h+var_1F4], eax
0x1800162a9  lea     rax, [rsp+230h+var_1F4]
0x1800162ae  mov     [rbp+130h+var_A0], rax
0x1800162b5  mov     eax, dword ptr [rbp+130h+arg_38]
0x1800162bb  mov     dword ptr [rsp+230h+var_1F0], eax
0x1800162bf  lea     rax, [rsp+230h+var_1F0]
0x1800162c4  mov     [rbp+130h+var_90], rax
0x1800162cb  mov     al, byte ptr [rbp+130h+arg_40]
0x1800162d1  mov     byte ptr [rsp+230h+var_200], al
0x1800162d5  lea     rax, [rsp+230h+var_200]
0x1800162da  mov     [rbp+130h+var_80], rax
0x1800162e1  mov     al, byte ptr [rbp+130h+arg_48]
0x1800162e7  mov     byte ptr [rsp+230h+var_200+1], al
0x1800162eb  lea     rax, [rsp+230h+var_200+1]
0x1800162f0  mov     [rbp+130h+var_70], rax
0x1800162f7  mov     al, byte ptr [rbp+130h+arg_50]
0x1800162fd  mov     byte ptr [rsp+230h+var_200+2], al
0x180016301  lea     rax, [rsp+230h+var_200+2]
0x180016306  mov     [rbp+130h+var_60], rax
0x18001630d  mov     al, byte ptr [rbp+130h+arg_58]
0x180016313  mov     byte ptr [rsp+230h+var_200+3], al
0x180016317  lea     rax, [rsp+230h+var_200+3]
0x18001631c  mov     [rbp+130h+var_50], rax
0x180016323  lea     rax, [rsp+230h+var_1E8]
0x180016328  mov     [rbp+130h+var_40], rax
0x18001632f  lea     rax, [rbp+130h+var_120]
0x180016333  mov     [rsp+230h+var_208], rax; __int64
0x180016338  mov     [rsp+230h+var_210], 0Fh; ULONG
0x180016340  mov     [rbp+130h+var_F8], 4
0x180016348  mov     [rbp+130h+var_E8], 4
0x180016350  mov     [rbp+130h+var_D8], 8
0x180016358  mov     [rbp+130h+var_C8], 8
0x180016360  mov     [rbp+130h+var_B8], 8
0x180016368  mov     [rbp+130h+var_A8], 8
0x180016373  mov     [rbp+130h+var_98], 4
0x18001637e  mov     [rbp+130h+var_88], 4
0x180016389  mov     [rbp+130h+var_78], 1
0x180016394  mov     [rbp+130h+var_68], 1
0x18001639f  mov     [rbp+130h+var_58], 1
0x1800163aa  mov     [rbp+130h+var_48], 1
0x1800163b5  mov     [rsp+230h+var_1E8], 1000000h
0x1800163be  mov     [rbp+130h+var_38], 8
0x1800163c9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800163ce  mov     rcx, [rbp+130h+var_30]
0x1800163d5  xor     rcx, rsp; StackCookie
0x1800163d8  call    __security_check_cookie
0x1800163dd  add     rsp, 210h
0x1800163e4  pop     r14
0x1800163e6  pop     rdi
0x1800163e7  pop     rsi
0x1800163e8  pop     rbx
0x1800163e9  pop     rbp
0x1800163ea  retn
```
