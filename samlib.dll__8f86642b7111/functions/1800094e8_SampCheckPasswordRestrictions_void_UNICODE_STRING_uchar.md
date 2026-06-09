# SampCheckPasswordRestrictions(void *,_UNICODE_STRING *,uchar *)

- ea: `0x1800094e8`
- end: `0x18000958c`
- name: `?SampCheckPasswordRestrictions@@YAJPEAXPEAU_UNICODE_STRING@@PEAE@Z`
- size: `164`
- prototype: `int(void *, struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040e0`
- `0x18000b1c4`
- `0x18000ccb0`

## callees

- `0x1800094e8`
- `0x180009594`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180009540`
- `RPCRT4!NdrClientCall3` at `0x180009540`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SampCheckPasswordRestrictions(void *a1, struct _UNICODE_STRING *a2, unsigned __int8 *a3)
{
  USHORT Length; // ax
  CLIENT_CALL_RETURN result; // rax
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  Length = a2->Length;
  v7 = 0;
  if ( !Length )
    return 0;
  if ( (Length & 0xFFFEu) > 0x200 )
    return (CLIENT_CALL_RETURN)3221225580LL;
  *a3 = 0;
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x2Cu, 0, a1, &v7).Pointer;
  if ( SLODWORD(result.Simple) < 0 )
    return result;
  if ( (unsigned __int16)(a2->Length >> 1) >= (unsigned __int16)v7 )
  {
    if ( (v7 & 0x400000000LL) != 0 )
      *a3 = 1;
    if ( (v7 & 0x100000000LL) != 0 && (a2->Length & 1) == 0 )
      return (CLIENT_CALL_RETURN)SampCheckStrongPasswordRestrictions(a2);
  }
  else
  {
    return (CLIENT_CALL_RETURN)3221225580LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800094e8  mov     [rsp+arg_0], rbx
0x1800094ed  mov     [rsp+arg_10], rsi
0x1800094f2  push    rdi
0x1800094f3  sub     rsp, 30h
0x1800094f7  movzx   eax, word ptr [rdx]
0x1800094fa  xor     esi, esi
0x1800094fc  mov     [rsp+38h+arg_8], rsi
0x180009501  mov     rdi, r8
0x180009504  mov     rbx, rdx
0x180009507  test    ax, ax
0x18000950a  jnz     short loc_180009510
0x18000950c  xor     eax, eax
0x18000950e  jmp     short loc_18000957C
0x180009510  mov     edx, 0FFFEh
0x180009515  and     ax, dx
0x180009518  mov     edx, 200h
0x18000951d  cmp     ax, dx
0x180009520  ja      short loc_180009557
0x180009522  mov     [r8], sil
0x180009525  lea     rax, [rsp+38h+arg_8]
0x18000952a  xor     r8d, r8d; pReturnValue
0x18000952d  mov     [rsp+38h+var_18], rax
0x180009532  mov     r9, rcx
0x180009535  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000953c  lea     edx, [r8+2Ch]; nProcNum
0x180009540  call    cs:__imp_NdrClientCall3
0x180009546  test    eax, eax
0x180009548  js      short loc_18000957C
0x18000954a  movzx   ecx, word ptr [rbx]
0x18000954d  shr     cx, 1
0x180009550  cmp     cx, word ptr [rsp+38h+arg_8]
0x180009555  jnb     short loc_18000955E
0x180009557  mov     eax, 0C000006Ch
0x18000955c  jmp     short loc_18000957C
0x18000955e  test    byte ptr [rsp+38h+arg_8+4], 4
0x180009563  jz      short loc_180009568
0x180009565  mov     byte ptr [rdi], 1
0x180009568  test    byte ptr [rsp+38h+arg_8+4], 1
0x18000956d  jz      short loc_18000957C
0x18000956f  test    byte ptr [rbx], 1
0x180009572  jnz     short loc_18000957C
0x180009574  mov     rcx, rbx; struct _UNICODE_STRING *
0x180009577  call    ?SampCheckStrongPasswordRestrictions@@YAJPEAU_UNICODE_STRING@@@Z; SampCheckStrongPasswordRestrictions(_UNICODE_STRING *)
0x18000957c  mov     rbx, [rsp+38h+arg_0]
0x180009581  mov     rsi, [rsp+38h+arg_10]
0x180009586  add     rsp, 30h
0x18000958a  pop     rdi
0x18000958b  retn
```
