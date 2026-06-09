# AllocDitherBuffers(long,ERRBUF * *,ERRBUF * *)

- ea: `0x1800354e8`
- end: `0x18003556f`
- name: `?AllocDitherBuffers@@YAJJPEAPEAUERRBUF@@0@Z`
- size: `135`
- prototype: `__int64 __fastcall(int, struct ERRBUF **, struct ERRBUF **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010a64`

## callees

- `0x1800354e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035529`

## pseudocode

```c
__int64 __fastcall AllocDitherBuffers(unsigned int a1, struct ERRBUF **a2, struct ERRBUF **a3)
{
  __int64 v3; // rax
  char *v7; // rax
  char *v8; // rdx
  __int64 result; // rax

  v3 = a1 + 2;
  *a3 = 0;
  *a2 = 0;
  if ( (unsigned int)v3 < a1 || (unsigned __int64)(24 * v3) > 0xFFFFFFFF )
    return 2147942934LL;
  v7 = (char *)CoTaskMemAlloc((unsigned int)(24 * v3));
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *a2 = (struct ERRBUF *)(v7 + 12);
  result = 0;
  *a3 = (struct ERRBUF *)&v8[12 * (a1 + 3)];
  return result;
}

```

## disassembly

```asm
0x1800354e8  mov     [rsp+arg_0], rbx
0x1800354ed  mov     [rsp+arg_8], rsi
0x1800354f2  push    rdi
0x1800354f3  sub     rsp, 20h
0x1800354f7  lea     eax, [rcx+2]
0x1800354fa  mov     qword ptr [r8], 0
0x180035501  mov     qword ptr [rdx], 0
0x180035508  mov     rdi, r8
0x18003550b  mov     rsi, rdx
0x18003550e  mov     ebx, ecx
0x180035510  cmp     eax, ecx
0x180035512  jb      short loc_18003555A
0x180035514  lea     r9, [rax+rax*2]
0x180035518  mov     eax, 0FFFFFFFFh
0x18003551d  shl     r9, 3
0x180035521  cmp     r9, rax
0x180035524  ja      short loc_18003555A
0x180035526  mov     ecx, r9d; cb
0x180035529  call    cs:__imp_CoTaskMemAlloc
0x18003552f  mov     rdx, rax
0x180035532  test    rax, rax
0x180035535  jnz     short loc_18003553E
0x180035537  mov     eax, 8007000Eh
0x18003553c  jmp     short loc_18003555F
0x18003553e  add     rax, 0Ch
0x180035542  mov     [rsi], rax
0x180035545  lea     eax, [rbx+3]
0x180035548  movsxd  rcx, eax
0x18003554b  lea     rax, [rcx+rcx*2]
0x18003554f  lea     rcx, [rdx+rax*4]
0x180035553  xor     eax, eax
0x180035555  mov     [rdi], rcx
0x180035558  jmp     short loc_18003555F
0x18003555a  mov     eax, 80070216h
0x18003555f  mov     rbx, [rsp+28h+arg_0]
0x180035564  mov     rsi, [rsp+28h+arg_8]
0x180035569  add     rsp, 20h
0x18003556d  pop     rdi
0x18003556e  retn
```
