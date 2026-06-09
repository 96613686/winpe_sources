# LoadSubscription

- ea: `0x18000e28c`
- end: `0x18000e3be`
- name: `LoadSubscription`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000f2c0`
- `0x1800173f0`
- `0x180017ab0`
- `0x180017f40`

## callees

- `0x18000c740`
- `0x18000cc84`
- `0x18000dd40`
- `0x18000e28c`
- `0x18001c384`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000e33f`
- `ole32!CoTaskMemAlloc` at `0x18000e33f`

## pseudocode

```c
__int64 __fastcall LoadSubscription(const unsigned __int16 *a1, unsigned __int16 **a2, __int64 a3, unsigned int a4)
{
  unsigned int v6; // esi
  unsigned int v7; // r9d
  unsigned __int16 v8; // r14
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  GUID iid; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+44h] [rbp-BCh]
  __int64 v16; // [rsp+4Ch] [rbp-B4h]

  v15 = 0;
  v16 = 0;
  v12 = 0;
  iid = 0;
  if ( (unsigned int)ReadCookieFromInetDB(a1, &iid, a3, a4) )
    return (unsigned int)-2147467259;
  v6 = LoadWithCookie(a1, (struct OOEBuf *)v14, &v12, &iid);
  if ( v6 )
  {
    WriteCookieToInetDB(a1, 0, 1, v7);
    return (unsigned int)-2147467259;
  }
  if ( v12 > 0xFFFF
    || (v8 = v12 + 224, (unsigned __int16)(v12 + 224) < (unsigned __int16)v12)
    || (unsigned __int64)v8 + 2 < v8 )
  {
    v10 = 0;
    goto LABEL_9;
  }
  v9 = (unsigned __int16 *)CoTaskMemAlloc(v8 + 2LL);
  v10 = v9;
  if ( !v9 )
  {
LABEL_9:
    *a2 = v10;
    return 2147942414LL;
  }
  memset_0(v9, 0, v8 + 2LL);
  *v10 = v8;
  v10[1] = 29701;
  *a2 = v10;
  CopyToMyPooe(v14, v10 + 4);
  return v6;
}

```

## disassembly

```asm
0x18000e28c  mov     [rsp-8+arg_10], rbx
0x18000e291  push    rbp
0x18000e292  push    rsi
0x18000e293  push    rdi
0x18000e294  push    r14
0x18000e296  push    r15
0x18000e298  lea     rbp, [rsp-14E0h]
0x18000e2a0  mov     eax, 15E0h
0x18000e2a5  call    _alloca_probe
0x18000e2aa  sub     rsp, rax
0x18000e2ad  mov     rax, cs:__security_cookie
0x18000e2b4  xor     rax, rsp
0x18000e2b7  mov     [rbp+1500h+var_30], rax
0x18000e2be  mov     rdi, rdx
0x18000e2c1  mov     [rsp+1600h+var_15BC], 0
0x18000e2ca  xorps   xmm0, xmm0
0x18000e2cd  mov     [rsp+1600h+var_15B4], 0
0x18000e2d6  lea     rdx, [rsp+1600h+iid]; lpiid
0x18000e2db  mov     [rsp+1600h+var_15E0], 0
0x18000e2e3  movups  xmmword ptr [rsp+1600h+iid.Data1], xmm0
0x18000e2e8  mov     rbx, rcx
0x18000e2eb  call    ?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z; ReadCookieFromInetDB(ushort const *,_GUID *)
0x18000e2f0  test    eax, eax
0x18000e2f2  jnz     loc_18000E391
0x18000e2f8  lea     r9, [rsp+1600h+iid]; struct _GUID *
0x18000e2fd  mov     rcx, rbx; psz2
0x18000e300  lea     r8, [rsp+1600h+var_15E0]; unsigned int *
0x18000e305  lea     rdx, [rsp+1600h+var_15C0]; struct OOEBuf *
0x18000e30a  call    ?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z; LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)
0x18000e30f  mov     esi, eax
0x18000e311  test    eax, eax
0x18000e313  jnz     short loc_18000E383
0x18000e315  mov     eax, [rsp+1600h+var_15E0]
0x18000e319  cmp     eax, 0FFFFh
0x18000e31e  ja      short loc_18000E377
0x18000e320  mov     r14d, 0E0h
0x18000e326  add     r14d, eax
0x18000e329  cmp     r14w, ax
0x18000e32d  jb      short loc_18000E377
0x18000e32f  movzx   eax, r14w
0x18000e333  lea     r15, [rax+2]
0x18000e337  cmp     r15, rax
0x18000e33a  jb      short loc_18000E377
0x18000e33c  mov     rcx, r15; cb
0x18000e33f  call    cs:__imp_CoTaskMemAlloc
0x18000e345  mov     rbx, rax
0x18000e348  test    rax, rax
0x18000e34b  jz      short loc_18000E379
0x18000e34d  mov     r8, r15; Size
0x18000e350  xor     edx, edx; Val
0x18000e352  mov     rcx, rax; void *
0x18000e355  call    memset_0
0x18000e35a  mov     [rbx], r14w
0x18000e35e  lea     rdx, [rbx+8]
0x18000e362  mov     word ptr [rbx+2], 7405h
0x18000e368  lea     rcx, [rsp+1600h+var_15C0]
0x18000e36d  mov     [rdi], rbx
0x18000e370  call    CopyToMyPooe
0x18000e375  jmp     short loc_18000E396
0x18000e377  xor     ebx, ebx
0x18000e379  mov     [rdi], rbx
0x18000e37c  mov     eax, 8007000Eh
0x18000e381  jmp     short loc_18000E398
0x18000e383  xor     edx, edx; rclsid
0x18000e385  mov     rcx, rbx; unsigned __int16 *
0x18000e388  lea     r8d, [rdx+1]; int
0x18000e38c  call    ?WriteCookieToInetDB@@YAJPEBGPEBU_GUID@@H@Z; WriteCookieToInetDB(ushort const *,_GUID const *,int)
0x18000e391  mov     esi, 80004005h
0x18000e396  mov     eax, esi
0x18000e398  mov     rcx, [rbp+1500h+var_30]
0x18000e39f  xor     rcx, rsp; StackCookie
0x18000e3a2  call    __security_check_cookie
0x18000e3a7  mov     rbx, [rsp+1600h+arg_10]
0x18000e3af  add     rsp, 15E0h
0x18000e3b6  pop     r15
0x18000e3b8  pop     r14
0x18000e3ba  pop     rdi
0x18000e3bb  pop     rsi
0x18000e3bc  pop     rbp
0x18000e3bd  retn
```
