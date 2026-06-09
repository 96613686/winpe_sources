# CVssJetWriter::`vector deleting destructor'(uint)

- ea: `0x180002060`
- end: `0x180002101`
- name: `??_ECVssJetWriter@@UEAAPEAXI@Z`
- size: `161`
- prototype: `void *__fastcall(CVssJetWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002060`

## import_xrefs

- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x18000209a`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x1800020c6`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x18000209a`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x1800020c6`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800020b5`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800020db`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800020b5`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800020db`

## pseudocode

```c
CVssJetWriter *__fastcall CVssJetWriter::`vector deleting destructor'(CVssJetWriter *this, char a2)
{
  char *v4; // r14
  __int64 v5; // rdi
  CVssJetWriter *i; // rbx

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (CVssJetWriter *)((char *)this + 24 * v5); v5; --v5 )
    {
      i = (CVssJetWriter *)((char *)i - 24);
      CVssJetWriter::~CVssJetWriter(i);
    }
    if ( (a2 & 1) != 0 )
      WdsPrivateHpFree(v4);
    return (CVssJetWriter *)v4;
  }
  else
  {
    CVssJetWriter::~CVssJetWriter(this);
    if ( (a2 & 1) != 0 )
      WdsPrivateHpFree(this);
    return this;
  }
}

```

## disassembly

```asm
0x180002060  mov     [rsp+arg_0], rbx
0x180002065  mov     [rsp+arg_8], rsi
0x18000206a  mov     [rsp+arg_10], rdi
0x18000206f  push    r14
0x180002071  sub     rsp, 20h
0x180002075  mov     esi, edx
0x180002077  mov     rbx, rcx
0x18000207a  test    dl, 2
0x18000207d  jz      short loc_1800020C6
0x18000207f  lea     r14, [rcx-8]
0x180002083  mov     rdi, [r14]
0x180002086  lea     rax, [rdi+rdi*2]
0x18000208a  lea     rbx, [rcx+rax*8]
0x18000208e  test    rdi, rdi
0x180002091  jz      short loc_1800020AC
0x180002093  sub     rbx, 18h
0x180002097  mov     rcx, rbx
0x18000209a  call    cs:__imp_??1CVssJetWriter@@UEAA@XZ; CVssJetWriter::~CVssJetWriter(void)
0x1800020a1  nop     dword ptr [rax+rax+00h]
0x1800020a6  sub     rdi, 1
0x1800020aa  jnz     short loc_180002093
0x1800020ac  test    sil, 1
0x1800020b0  jz      short loc_1800020C1
0x1800020b2  mov     rcx, r14
0x1800020b5  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800020bc  nop     dword ptr [rax+rax+00h]
0x1800020c1  mov     rax, r14
0x1800020c4  jmp     short loc_1800020EA
0x1800020c6  call    cs:__imp_??1CVssJetWriter@@UEAA@XZ; CVssJetWriter::~CVssJetWriter(void)
0x1800020cd  nop     dword ptr [rax+rax+00h]
0x1800020d2  test    sil, 1
0x1800020d6  jz      short loc_1800020E7
0x1800020d8  mov     rcx, rbx
0x1800020db  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800020e2  nop     dword ptr [rax+rax+00h]
0x1800020e7  mov     rax, rbx
0x1800020ea  mov     rbx, [rsp+28h+arg_0]
0x1800020ef  mov     rsi, [rsp+28h+arg_8]
0x1800020f4  mov     rdi, [rsp+28h+arg_10]
0x1800020f9  add     rsp, 20h
0x1800020fd  pop     r14
0x1800020ff  retn
```
