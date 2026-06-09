# GetDLFromTN(IMSASRLocaleHandler *,ushort const *,ushort * *,ushort * *)

- ea: `0x1800f5d4c`
- end: `0x1800f5ded`
- name: `?GetDLFromTN@@YAJPEAUIMSASRLocaleHandler@@PEBGPEAPEAG2@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct IMSASRLocaleHandler *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f5430`

## callees

- `0x1800f5d4c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5dda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5dda`

## pseudocode

```c
__int64 __fastcall GetDLFromTN(
        struct IMSASRLocaleHandler *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 v4; // rax
  __int64 v7; // r8
  int v9; // ebx
  __int128 v11; // [rsp+40h] [rbp-58h] BYREF
  __int128 v12; // [rsp+50h] [rbp-48h]
  LPVOID pv[2]; // [rsp+60h] [rbp-38h]

  v4 = *(_QWORD *)a1;
  v7 = -1;
  v11 = 0;
  v12 = 0;
  *(_OWORD *)pv = 0;
  do
    ++v7;
  while ( a2[v7] );
  v9 = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, const unsigned __int16 *, __int64, _QWORD, __int128 *))(v4 + 80))(
         a1,
         a2,
         v7,
         0,
         &v11);
  if ( v9 >= 0 && (_DWORD)v11 == 1 )
    v9 = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, _QWORD, _QWORD, unsigned __int16 **, unsigned __int16 **, _QWORD))(*(_QWORD *)a1 + 48LL))(
           a1,
           *(_QWORD *)v12,
           0,
           a3,
           a4,
           0);
  CoTaskMemFree(pv[1]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800f5d4c  push    rbx
0x1800f5d4e  push    rbp
0x1800f5d4f  push    rsi
0x1800f5d50  push    rdi
0x1800f5d51  push    r14
0x1800f5d53  sub     rsp, 70h
0x1800f5d57  mov     rax, [rcx]
0x1800f5d5a  xorps   xmm0, xmm0
0x1800f5d5d  mov     rbp, r8
0x1800f5d60  mov     rsi, r9
0x1800f5d63  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f5d67  mov     rdi, rcx
0x1800f5d6a  xor     r14d, r14d
0x1800f5d6d  movups  [rsp+98h+var_58], xmm0
0x1800f5d72  movups  [rsp+98h+var_48], xmm0
0x1800f5d77  movups  xmmword ptr [rsp+98h+pv], xmm0
0x1800f5d7c  inc     r8
0x1800f5d7f  cmp     [rdx+r8*2], r14w
0x1800f5d84  jnz     short loc_1800F5D7C
0x1800f5d86  mov     rax, [rax+50h]
0x1800f5d8a  lea     rcx, [rsp+98h+var_58]
0x1800f5d8f  mov     [rsp+98h+var_78], rcx
0x1800f5d94  xor     r9d, r9d
0x1800f5d97  mov     rcx, rdi
0x1800f5d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5d9f  mov     ebx, eax
0x1800f5da1  test    eax, eax
0x1800f5da3  js      short loc_1800F5DD5
0x1800f5da5  cmp     dword ptr [rsp+98h+var_58], 1
0x1800f5daa  jnz     short loc_1800F5DD5
0x1800f5dac  mov     rax, [rdi]
0x1800f5daf  mov     r9, rbp
0x1800f5db2  mov     rdx, qword ptr [rsp+98h+var_48]
0x1800f5db7  xor     r8d, r8d
0x1800f5dba  mov     [rsp+98h+var_70], r14
0x1800f5dbf  mov     rcx, rdi
0x1800f5dc2  mov     [rsp+98h+var_78], rsi
0x1800f5dc7  mov     rax, [rax+30h]
0x1800f5dcb  mov     rdx, [rdx]
0x1800f5dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5dd3  mov     ebx, eax
0x1800f5dd5  mov     rcx, [rsp+98h+pv+8]; pv
0x1800f5dda  call    cs:__imp_CoTaskMemFree
0x1800f5de0  mov     eax, ebx
0x1800f5de2  add     rsp, 70h
0x1800f5de6  pop     r14
0x1800f5de8  pop     rdi
0x1800f5de9  pop     rsi
0x1800f5dea  pop     rbp
0x1800f5deb  pop     rbx
0x1800f5dec  retn
```
