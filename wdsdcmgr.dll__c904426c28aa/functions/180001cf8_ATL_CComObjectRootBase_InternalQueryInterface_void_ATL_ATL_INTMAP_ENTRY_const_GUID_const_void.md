# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180001cf8`
- end: `0x180001e0e`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `278`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001aa0`
- `0x180007ab0`
- `0x180008480`
- `0x18000e2f0`
- `0x180011430`
- `0x180012520`

## callees

- `0x180001cf8`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  unsigned int v4; // edi
  __int64 v8; // rbx
  char *v9; // rbx
  _QWORD *i; // rsi
  _DWORD *v11; // rbp
  int v12; // eax

  v4 = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v8 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  for ( i = (_QWORD *)((char *)a2 + 16); ; i += 3 )
  {
    if ( !*i )
      return (unsigned int)-2147467262;
    v11 = (_DWORD *)*(i - 2);
    if ( v11
      && (*v11 != a3->Data1
       || v11[1] != *(_DWORD *)&a3->Data2
       || v11[2] != *(_DWORD *)a3->Data4
       || v11[3] != *(_DWORD *)&a3->Data4[4]) )
    {
      continue;
    }
    if ( *i == 1 )
      break;
    v12 = ((__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*i)(a1, a3, a4, *(i - 1));
    if ( !v12 || v11 && v12 < 0 )
      return (unsigned int)v12;
  }
  v8 = *(i - 1);
LABEL_9:
  v9 = &a1[v8];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
  *a4 = v9;
  return v4;
}

```

## disassembly

```asm
0x180001cf8  mov     [rsp+arg_0], rbx
0x180001cfd  mov     [rsp+arg_8], rbp
0x180001d02  mov     [rsp+arg_10], rsi
0x180001d07  push    rdi
0x180001d08  push    r14
0x180001d0a  push    r15
0x180001d0c  sub     rsp, 30h
0x180001d10  xor     edi, edi
0x180001d12  mov     r14, r9
0x180001d15  mov     rbx, r8
0x180001d18  mov     r15, rcx
0x180001d1b  test    rcx, rcx
0x180001d1e  jz      loc_180001DEE
0x180001d24  test    rdx, rdx
0x180001d27  jz      loc_180001DEE
0x180001d2d  test    r9, r9
0x180001d30  jnz     short loc_180001D3C
0x180001d32  mov     edi, 80004003h
0x180001d37  jmp     loc_180001DF3
0x180001d3c  mov     [r9], rdi
0x180001d3f  cmp     [r8], edi
0x180001d42  jnz     short loc_180001D7A
0x180001d44  cmp     [r8+4], edi
0x180001d48  jnz     short loc_180001D7A
0x180001d4a  cmp     dword ptr [r8+8], 0C0h
0x180001d52  jnz     short loc_180001D7A
0x180001d54  cmp     dword ptr [r8+0Ch], 46000000h
0x180001d5c  jnz     short loc_180001D7A
0x180001d5e  mov     rbx, [rdx+8]
0x180001d62  add     rbx, r15
0x180001d65  mov     rcx, rbx
0x180001d68  mov     rax, [rbx]
0x180001d6b  mov     rax, [rax+8]
0x180001d6f  call    cs:__guard_dispatch_icall_fptr
0x180001d75  mov     [r14], rbx
0x180001d78  jmp     short loc_180001DF3
0x180001d7a  lea     rsi, [rdx+10h]
0x180001d7e  jmp     short loc_180001DD5
0x180001d80  mov     rbp, [rsi-10h]
0x180001d84  test    rbp, rbp
0x180001d87  jz      short loc_180001DA8
0x180001d89  mov     eax, [rbx]
0x180001d8b  cmp     [rbp+0], eax
0x180001d8e  jnz     short loc_180001DD1
0x180001d90  mov     eax, [rbx+4]
0x180001d93  cmp     [rbp+4], eax
0x180001d96  jnz     short loc_180001DD1
0x180001d98  mov     eax, [rbx+8]
0x180001d9b  cmp     [rbp+8], eax
0x180001d9e  jnz     short loc_180001DD1
0x180001da0  mov     eax, [rbx+0Ch]
0x180001da3  cmp     [rbp+0Ch], eax
0x180001da6  jnz     short loc_180001DD1
0x180001da8  cmp     qword ptr [rsi], 1
0x180001dac  jz      short loc_180001DE5
0x180001dae  mov     r9, [rsi-8]
0x180001db2  mov     r8, r14
0x180001db5  mov     rax, [rsi]
0x180001db8  mov     rdx, rbx
0x180001dbb  mov     rcx, r15
0x180001dbe  call    cs:__guard_dispatch_icall_fptr
0x180001dc4  test    eax, eax
0x180001dc6  jz      short loc_180001DE1
0x180001dc8  test    rbp, rbp
0x180001dcb  jz      short loc_180001DD1
0x180001dcd  test    eax, eax
0x180001dcf  js      short loc_180001DE1
0x180001dd1  add     rsi, 18h
0x180001dd5  cmp     [rsi], rdi
0x180001dd8  jnz     short loc_180001D80
0x180001dda  mov     edi, 80004002h
0x180001ddf  jmp     short loc_180001DF3
0x180001de1  mov     edi, eax
0x180001de3  jmp     short loc_180001DF3
0x180001de5  mov     rbx, [rsi-8]
0x180001de9  jmp     loc_180001D62
0x180001dee  mov     edi, 80070057h
0x180001df3  mov     rbx, [rsp+48h+arg_0]
0x180001df8  mov     eax, edi
0x180001dfa  mov     rbp, [rsp+48h+arg_8]
0x180001dff  mov     rsi, [rsp+48h+arg_10]
0x180001e04  add     rsp, 30h
0x180001e08  pop     r15
0x180001e0a  pop     r14
0x180001e0c  pop     rdi
0x180001e0d  retn
```
