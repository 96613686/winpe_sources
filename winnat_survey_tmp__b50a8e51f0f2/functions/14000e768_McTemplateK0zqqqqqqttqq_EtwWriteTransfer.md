# McTemplateK0zqqqqqqttqq_EtwWriteTransfer

- ea: `0x14000e768`
- end: `0x14000e89c`
- name: `McTemplateK0zqqqqqqttqq_EtwWriteTransfer`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400110d0`

## callees

- `0x1400095bc`
- `0x14000e768`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqqqqqqttqq_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14)
{
  __int64 v14; // rax
  int v15; // eax
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-C9h] BYREF
  const wchar_t *v18; // [rsp+40h] [rbp-B9h]
  int v19; // [rsp+48h] [rbp-B1h]
  int v20; // [rsp+4Ch] [rbp-ADh]
  char *v21; // [rsp+50h] [rbp-A9h]
  __int64 v22; // [rsp+58h] [rbp-A1h]
  char *v23; // [rsp+60h] [rbp-99h]
  __int64 v24; // [rsp+68h] [rbp-91h]
  char *v25; // [rsp+70h] [rbp-89h]
  __int64 v26; // [rsp+78h] [rbp-81h]
  char *v27; // [rsp+80h] [rbp-79h]
  __int64 v28; // [rsp+88h] [rbp-71h]
  char *v29; // [rsp+90h] [rbp-69h]
  __int64 v30; // [rsp+98h] [rbp-61h]
  char *v31; // [rsp+A0h] [rbp-59h]
  __int64 v32; // [rsp+A8h] [rbp-51h]
  char *v33; // [rsp+B0h] [rbp-49h]
  __int64 v34; // [rsp+B8h] [rbp-41h]
  char *v35; // [rsp+C0h] [rbp-39h]
  __int64 v36; // [rsp+C8h] [rbp-31h]
  char *v37; // [rsp+D0h] [rbp-29h]
  __int64 v38; // [rsp+D8h] [rbp-21h]
  char *v39; // [rsp+E0h] [rbp-19h]
  __int64 v40; // [rsp+E8h] [rbp-11h]

  if ( a4 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a4[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v19 = v15;
  v20 = 0;
  v22 = 4;
  v21 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v18 = a4;
  v23 = &a6;
  v24 = 4;
  v25 = &a7;
  v26 = 4;
  v27 = &a8;
  v29 = &a9;
  v31 = &a10;
  v33 = &a11;
  v35 = &a12;
  v37 = &a13;
  v39 = &a14;
  v28 = 4;
  v30 = 4;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNAT_INSTANCE_EVENT, 0, 0xCu, &v17);
}

```

## disassembly

```asm
0x14000e768  push    rbp
0x14000e76a  lea     rbp, [rsp-7]
0x14000e76f  sub     rsp, 100h
0x14000e776  mov     rax, cs:__security_cookie
0x14000e77d  xor     rax, rsp
0x14000e780  mov     [rbp+7+var_10], rax
0x14000e784  xor     r8d, r8d
0x14000e787  test    r9, r9
0x14000e78a  jz      short loc_14000E7A3
0x14000e78c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e790  inc     rax
0x14000e793  cmp     [r9+rax*2], r8w
0x14000e798  jnz     short loc_14000E790
0x14000e79a  lea     eax, ds:2[rax*2]
0x14000e7a1  jmp     short loc_14000E7A8
0x14000e7a3  mov     eax, 0Ah
0x14000e7a8  mov     [rsp+100h+var_B8], eax
0x14000e7ac  lea     rdx, aNull; "NULL"
0x14000e7b3  test    r9, r9
0x14000e7b6  mov     [rsp+100h+var_B4], r8d
0x14000e7bb  lea     rax, [rbp+7+arg_20]
0x14000e7bf  mov     [rsp+100h+var_A8], 4
0x14000e7c8  mov     [rsp+100h+var_B0], rax
0x14000e7cd  cmovz   r9, rdx
0x14000e7d1  lea     rax, [rbp+7+arg_28]
0x14000e7d5  mov     [rsp+100h+var_C0], r9
0x14000e7da  mov     [rsp+100h+var_A0], rax
0x14000e7df  lea     rdx, WINNAT_INSTANCE_EVENT
0x14000e7e6  lea     rax, [rbp+7+arg_30]
0x14000e7ea  mov     [rsp+100h+var_98], 4
0x14000e7f3  mov     [rsp+100h+var_90], rax
0x14000e7f8  mov     r9d, 0Ch
0x14000e7fe  lea     rax, [rbp+7+arg_38]
0x14000e802  mov     [rsp+100h+var_88], 4
0x14000e80b  mov     [rbp+7+var_80], rax
0x14000e80f  lea     rax, [rbp+7+arg_40]
0x14000e813  mov     [rbp+7+var_70], rax
0x14000e817  lea     rax, [rbp+7+arg_48]
0x14000e81b  mov     [rbp+7+var_60], rax
0x14000e81f  lea     rax, [rbp+7+arg_50]
0x14000e823  mov     [rbp+7+var_50], rax
0x14000e827  lea     rax, [rbp+7+arg_58]
0x14000e82b  mov     [rbp+7+var_40], rax
0x14000e82f  lea     rax, [rbp+7+arg_60]
0x14000e833  mov     [rbp+7+var_30], rax
0x14000e837  lea     rax, [rbp+7+arg_68]
0x14000e83b  mov     [rbp+7+var_20], rax
0x14000e83f  lea     rax, [rsp+100h+var_D0]
0x14000e844  mov     [rsp+100h+var_E0], rax
0x14000e849  mov     [rbp+7+var_78], 4
0x14000e851  mov     [rbp+7+var_68], 4
0x14000e859  mov     [rbp+7+var_58], 4
0x14000e861  mov     [rbp+7+var_48], 4
0x14000e869  mov     [rbp+7+var_38], 4
0x14000e871  mov     [rbp+7+var_28], 4
0x14000e879  mov     [rbp+7+var_18], 4
0x14000e881  call    McGenEventWrite_EtwWriteTransfer
0x14000e886  mov     rcx, [rbp+7+var_10]
0x14000e88a  xor     rcx, rsp; StackCookie
0x14000e88d  call    __security_check_cookie
0x14000e892  add     rsp, 100h
0x14000e899  pop     rbp
0x14000e89a  retn
```
