# HTTP2Channel::HTTP2Channel(int)

- ea: `0x180002360`
- end: `0x1800023ab`
- name: `??0HTTP2Channel@@QEAA@H@Z`
- size: `75`
- prototype: `HTTP2Channel *__fastcall(HTTP2Channel *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002468`
- `0x180002770`
- `0x180002874`
- `0x180002a40`
- `0x1800048d8`
- `0x180004fc8`

## callees

- `0x180019468`

## pseudocode

```c
HTTP2Channel *__fastcall HTTP2Channel::HTTP2Channel(HTTP2Channel *this, int a2)
{
  CompositeFlags *v3; // rcx
  HTTP2Channel *v4; // r8

  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &HTTP2ProxyServerSideChannel::`vftable';
  *((_DWORD *)this + 9) = 1;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 14) = 0;
  v3 = (HTTP2Channel *)((char *)this + 60);
  *(_DWORD *)v3 = 0;
  *((_QWORD *)this + 8) = 0;
  CompositeFlags::SetFlagUnsafe(v3, a2);
  return v4;
}

```

## disassembly

```asm
0x180002360  sub     rsp, 28h
0x180002364  xor     r9d, r9d
0x180002367  lea     rax, ??_7HTTP2ProxyServerSideChannel@@6B@; const HTTP2ProxyServerSideChannel::`vftable'
0x18000236e  mov     [rcx+18h], r9
0x180002372  mov     r8, rcx
0x180002375  mov     [rcx+8], r9
0x180002379  mov     [rcx+10h], r9
0x18000237d  mov     [rcx], rax
0x180002380  mov     dword ptr [rcx+24h], 1
0x180002387  mov     [rcx+28h], r9d
0x18000238b  mov     [rcx+2Ch], r9d
0x18000238f  mov     [rcx+38h], r9d
0x180002393  add     rcx, 3Ch ; '<'; this
0x180002397  mov     [rcx], r9d
0x18000239a  mov     [r8+40h], r9
0x18000239e  call    ?SetFlagUnsafe@CompositeFlags@@QEAAXI@Z; CompositeFlags::SetFlagUnsafe(uint)
0x1800023a3  mov     rax, r8
0x1800023a6  add     rsp, 28h
0x1800023aa  retn
```
