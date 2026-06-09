# McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer

- ea: `0x1400093f0`
- end: `0x1400095b5`
- name: `McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400077fc`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        int a13,
        int a14,
        char a15,
        int a16,
        int a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-D0h] BYREF
  int *v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  char *v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  char *v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  char *v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  char *v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  char *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  char *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  char *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  char *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  int *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  int *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  char *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  int *v49; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]
  __int64 v51; // [rsp+120h] [rbp+20h]
  int v52; // [rsp+128h] [rbp+28h]
  int v53; // [rsp+12Ch] [rbp+2Ch]
  __int64 v54; // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  int v56; // [rsp+13Ch] [rbp+3Ch]
  __int64 v57; // [rsp+140h] [rbp+40h]
  int v58; // [rsp+148h] [rbp+48h]
  int v59; // [rsp+14Ch] [rbp+4Ch]
  __int64 v60; // [rsp+150h] [rbp+50h]
  int v61; // [rsp+158h] [rbp+58h]
  int v62; // [rsp+15Ch] [rbp+5Ch]
  int v63; // [rsp+198h] [rbp+98h] BYREF

  v63 = a4;
  v24 = 4;
  v26 = 4;
  v23 = &v63;
  v28 = 4;
  v25 = &a5;
  v30 = 4;
  v27 = &a6;
  v29 = &a7;
  v31 = &a8;
  v33 = &a9;
  v35 = &a10;
  v37 = &a11;
  v39 = &a12;
  v41 = &a13;
  v43 = &a14;
  v45 = &a15;
  v47 = &a16;
  v49 = &a17;
  v51 = a18;
  v52 = a13;
  v54 = a19;
  v55 = a14;
  v57 = a20;
  v58 = a16;
  v60 = a21;
  v61 = a17;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 4;
  v42 = 4;
  v44 = 4;
  v46 = 4;
  v48 = 4;
  v50 = 4;
  v53 = 0;
  v56 = 0;
  v59 = 0;
  v62 = 0;
  return McGenEventWrite_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, a2, 0, 0x13u, &v22);
}

```

## disassembly

```asm
0x1400093f0  mov     [rsp-8+arg_18], r9d
0x1400093f5  push    rbp
0x1400093f6  lea     rbp, [rsp-70h]
0x1400093fb  sub     rsp, 170h
0x140009402  mov     rax, cs:__security_cookie
0x140009409  xor     rax, rsp
0x14000940c  mov     [rbp+70h+var_10], rax
0x140009410  xor     r8d, r8d
0x140009413  mov     [rsp+170h+var_128], 4
0x14000941c  lea     rax, [rbp+70h+arg_18]
0x140009423  mov     [rsp+170h+var_118], 4
0x14000942c  mov     [rsp+170h+var_130], rax
0x140009431  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140009438  lea     rax, [rbp+70h+arg_20]
0x14000943f  mov     [rsp+170h+var_108], 4
0x140009448  mov     [rsp+170h+var_120], rax
0x14000944d  lea     r9d, [r8+13h]
0x140009451  lea     rax, [rbp+70h+arg_28]
0x140009458  mov     [rsp+170h+var_F8], 4
0x140009461  mov     [rsp+170h+var_110], rax
0x140009466  lea     rax, [rbp+70h+arg_30]
0x14000946d  mov     [rsp+170h+var_100], rax
0x140009472  lea     rax, [rbp+70h+arg_38]
0x140009479  mov     [rbp+70h+var_F0], rax
0x14000947d  lea     rax, [rbp+70h+arg_40]
0x140009484  mov     [rbp+70h+var_E0], rax
0x140009488  lea     rax, [rbp+70h+arg_48]
0x14000948f  mov     [rbp+70h+var_D0], rax
0x140009493  lea     rax, [rbp+70h+arg_50]
0x14000949a  mov     [rbp+70h+var_C0], rax
0x14000949e  lea     rax, [rbp+70h+arg_58]
0x1400094a5  mov     [rbp+70h+var_B0], rax
0x1400094a9  lea     rax, [rbp+70h+arg_60]
0x1400094b0  mov     [rbp+70h+var_A0], rax
0x1400094b4  lea     rax, [rbp+70h+arg_68]
0x1400094bb  mov     [rbp+70h+var_90], rax
0x1400094bf  lea     rax, [rbp+70h+arg_70]
0x1400094c6  mov     [rbp+70h+var_80], rax
0x1400094ca  lea     rax, [rbp+70h+arg_78]
0x1400094d1  mov     [rbp+70h+var_70], rax
0x1400094d5  lea     rax, [rbp+70h+arg_80]
0x1400094dc  mov     [rbp+70h+var_60], rax
0x1400094e0  mov     rax, [rbp+70h+arg_88]
0x1400094e7  mov     [rbp+70h+var_50], rax
0x1400094eb  mov     eax, [rbp+70h+arg_60]
0x1400094f1  mov     [rbp+70h+var_48], eax
0x1400094f4  mov     rax, [rbp+70h+arg_90]
0x1400094fb  mov     [rbp+70h+var_40], rax
0x1400094ff  mov     eax, [rbp+70h+arg_68]
0x140009505  mov     [rbp+70h+var_38], eax
0x140009508  mov     rax, [rbp+70h+arg_98]
0x14000950f  mov     [rbp+70h+var_30], rax
0x140009513  mov     eax, [rbp+70h+arg_78]
0x140009519  mov     [rbp+70h+var_28], eax
0x14000951c  mov     rax, [rbp+70h+arg_A0]
0x140009523  mov     [rbp+70h+var_20], rax
0x140009527  mov     eax, [rbp+70h+arg_80]
0x14000952d  mov     [rbp+70h+var_18], eax
0x140009530  lea     rax, [rsp+170h+var_140]
0x140009535  mov     [rsp+170h+var_150], rax
0x14000953a  mov     [rbp+70h+var_E8], 4
0x140009542  mov     [rbp+70h+var_D8], 4
0x14000954a  mov     [rbp+70h+var_C8], 4
0x140009552  mov     [rbp+70h+var_B8], 4
0x14000955a  mov     [rbp+70h+var_A8], 4
0x140009562  mov     [rbp+70h+var_98], 4
0x14000956a  mov     [rbp+70h+var_88], 4
0x140009572  mov     [rbp+70h+var_78], 4
0x14000957a  mov     [rbp+70h+var_68], 4
0x140009582  mov     [rbp+70h+var_58], 4
0x14000958a  mov     [rbp+70h+var_44], r8d
0x14000958e  mov     [rbp+70h+var_34], r8d
0x140009592  mov     [rbp+70h+var_24], r8d
0x140009596  mov     [rbp+70h+var_14], r8d
0x14000959a  call    McGenEventWrite_EtwWriteTransfer
0x14000959f  mov     rcx, [rbp+70h+var_10]
0x1400095a3  xor     rcx, rsp; StackCookie
0x1400095a6  call    __security_check_cookie
0x1400095ab  add     rsp, 170h
0x1400095b2  pop     rbp
0x1400095b3  retn
```
