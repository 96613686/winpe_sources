# MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(wistd::integral_constant<char,0>)

- ea: `0x18000c3ac`
- end: `0x18000c475`
- name: `??$?0$$V@QueryWlidsvcProperties@MSAClientTraceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z`
- size: `201`
- prototype: `MSAClientTraceTelemetry::QueryWlidsvcProperties *__fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000cec8`

## callees

- `0x1800033b4`
- `0x18000d6dc`

## pseudocode

```c
MSAClientTraceTelemetry::QueryWlidsvcProperties *__fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  char *v2; // rbx
  _QWORD *v3; // rcx

  v2 = (char *)this + 8;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = "QueryWlidsvcProperties";
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 20) = 0;
  v3 = (_QWORD *)((char *)this + 88);
  v3[19] = 0;
  v3[20] = 0;
  memset_0(v3, 0, 0x98u);
  *((_DWORD *)v2 + 62) = 1;
  *((_QWORD *)v2 + 32) = 0;
  *((_QWORD *)this + 34) = v2;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = this;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = (char *)this + 48;
  *((_BYTE *)this + 328) = 0;
  *(_QWORD *)this = &MSAClientTraceTelemetry::QueryWlidsvcProperties::`vftable';
  MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(this);
  return this;
}

```

## disassembly

```asm
0x18000c3ac  mov     [rsp+arg_0], rbx
0x18000c3b1  mov     [rsp+arg_8], rsi
0x18000c3b6  push    rdi
0x18000c3b7  sub     rsp, 20h
0x18000c3bb  mov     rdi, rcx
0x18000c3be  lea     rbx, [rcx+8]
0x18000c3c2  xor     esi, esi
0x18000c3c4  mov     [rbx], esi
0x18000c3c6  mov     [rbx+4], sil
0x18000c3ca  mov     [rbx+40h], sil
0x18000c3ce  mov     [rbx+28h], esi
0x18000c3d1  lea     rax, aQuerywlidsvcpr; "QueryWlidsvcProperties"
0x18000c3d8  mov     [rbx+30h], rax
0x18000c3dc  mov     [rbx+38h], rsi
0x18000c3e0  mov     [rbx+48h], esi
0x18000c3e3  lea     rcx, [rbx+50h]; void *
0x18000c3e7  mov     [rcx+98h], rsi
0x18000c3ee  mov     [rcx+0A0h], rsi
0x18000c3f5  xor     edx, edx; Val
0x18000c3f7  mov     r8d, 98h; Size
0x18000c3fd  call    memset_0
0x18000c402  mov     dword ptr [rbx+0F8h], 1
0x18000c40c  xor     eax, eax
0x18000c40e  mov     [rbx+100h], rax
0x18000c415  mov     [rdi+110h], rbx
0x18000c41c  mov     [rdi+118h], rsi
0x18000c423  mov     [rdi+120h], rsi
0x18000c42a  mov     [rdi+128h], rdi
0x18000c431  mov     [rdi+130h], rsi
0x18000c438  mov     [rdi+138h], esi
0x18000c43e  lea     rax, [rdi+30h]
0x18000c442  mov     [rdi+140h], rax
0x18000c449  mov     [rdi+148h], sil
0x18000c450  lea     rax, ??_7QueryWlidsvcProperties@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::QueryWlidsvcProperties::`vftable'
0x18000c457  mov     [rdi], rax
0x18000c45a  mov     rcx, rdi; this
0x18000c45d  call    ?StartActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(void)
0x18000c462  mov     rax, rdi
0x18000c465  mov     rbx, [rsp+28h+arg_0]
0x18000c46a  mov     rsi, [rsp+28h+arg_8]
0x18000c46f  add     rsp, 20h
0x18000c473  pop     rdi
0x18000c474  retn
```
