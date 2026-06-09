# McTemplateU0qzz_EventWriteTransfer

- ea: `0x180013af8`
- end: `0x180013bcd`
- name: `McTemplateU0qzz_EventWriteTransfer`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011650`
- `0x18001385c`

## callees

- `0x180013a94`
- `0x180013af8`
- `0x18001c150`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        const char *a4,
        const char *a5)
{
  __int64 v5; // rax
  const char *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-50h] BYREF
  int *v14; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  const char *v16; // [rsp+50h] [rbp-30h]
  int v17; // [rsp+58h] [rbp-28h]
  int v18; // [rsp+5Ch] [rbp-24h]
  const char *v19; // [rsp+60h] [rbp-20h]
  int v20; // [rsp+68h] [rbp-18h]
  int v21; // [rsp+6Ch] [rbp-14h]
  int v22; // [rsp+A0h] [rbp+20h] BYREF

  v22 = a3;
  v15 = 4;
  v14 = &v22;
  v5 = -1;
  v7 = a5;
  v8 = 10;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&a4[2 * v9] );
    v10 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
    v10 = 10;
  }
  v17 = v10;
  v18 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v16 = a4;
  v11 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( *(_WORD *)&a5[2 * v5] );
    v8 = (unsigned int)(2 * v5 + 2);
    v11 = a5 == 0;
  }
  if ( v11 )
    v7 = L"NULL";
  v20 = v8;
  v19 = v7;
  v21 = 0;
  return McGenEventWrite_EventWriteTransfer(v10, a2, v8, (__int64)a4, &v13);
}

```

## disassembly

```asm
0x180013af8  mov     [rsp-8+arg_0], rbx
0x180013afd  mov     [rsp-8+arg_10], r8d
0x180013b02  push    rbp
0x180013b03  mov     rbp, rsp
0x180013b06  sub     rsp, 80h
0x180013b0d  mov     rax, cs:__security_cookie
0x180013b14  xor     rax, rsp
0x180013b17  mov     [rbp+var_10], rax
0x180013b1b  lea     rax, [rbp+arg_10]
0x180013b1f  mov     [rbp+var_38], 4
0x180013b27  xor     r11d, r11d
0x180013b2a  mov     [rbp+var_40], rax
0x180013b2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013b32  mov     r10, rdx
0x180013b35  mov     rdx, [rbp+arg_20]
0x180013b39  lea     r8d, [r11+0Ah]
0x180013b3d  test    r9, r9
0x180013b40  jz      short loc_180013B58
0x180013b42  mov     rcx, rax
0x180013b45  inc     rcx
0x180013b48  cmp     [r9+rcx*2], r11w
0x180013b4d  jnz     short loc_180013B45
0x180013b4f  lea     ecx, ds:2[rcx*2]
0x180013b56  jmp     short loc_180013B5B
0x180013b58  mov     ecx, r8d; int
0x180013b5b  test    r9, r9
0x180013b5e  mov     [rbp+var_28], ecx
0x180013b61  lea     rbx, aNull; "NULL"
0x180013b68  mov     [rbp+var_24], r11d
0x180013b6c  cmovz   r9, rbx; int
0x180013b70  mov     [rbp+var_30], r9
0x180013b74  test    rdx, rdx
0x180013b77  jz      short loc_180013B8E
0x180013b79  inc     rax
0x180013b7c  cmp     [rdx+rax*2], r11w
0x180013b81  jnz     short loc_180013B79
0x180013b83  lea     r8d, ds:2[rax*2]; int
0x180013b8b  test    rdx, rdx
0x180013b8e  cmovz   rdx, rbx
0x180013b92  mov     [rbp+var_18], r8d
0x180013b96  mov     [rbp+var_20], rdx
0x180013b9a  lea     rax, [rbp+var_50]
0x180013b9e  mov     rdx, r10; int
0x180013ba1  mov     [rbp+var_14], r11d
0x180013ba5  mov     [rsp+80h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x180013baa  call    McGenEventWrite_EventWriteTransfer
0x180013baf  mov     rcx, [rbp+var_10]
0x180013bb3  xor     rcx, rsp; StackCookie
0x180013bb6  call    __security_check_cookie
0x180013bbb  mov     rbx, [rsp+80h+arg_0]
0x180013bc3  add     rsp, 80h
0x180013bca  pop     rbp
0x180013bcb  retn
```
