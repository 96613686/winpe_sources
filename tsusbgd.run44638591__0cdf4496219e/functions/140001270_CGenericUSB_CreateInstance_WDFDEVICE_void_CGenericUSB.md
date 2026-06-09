# CGenericUSB::CreateInstance(WDFDEVICE__ *,void *,CGenericUSB * *)

- ea: `0x140001270`
- end: `0x1400012ff`
- name: `?CreateInstance@CGenericUSB@@SAJPEAUWDFDEVICE__@@PEAXPEAPEAV1@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, CGenericUSB *this, struct CGenericUSB **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c010`

## callees

- `0x140001188`
- `0x140001270`
- `0x140001464`

## pseudocode

```c
__int64 __fastcall CGenericUSB::CreateInstance(struct WDFDEVICE__ *a1, CGenericUSB *this, struct CGenericUSB **a3)
{
  int v5; // edi

  if ( this )
  {
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 9) = (char *)this + 64;
    *((_QWORD *)this + 8) = (char *)this + 64;
    v5 = CGenericUSB::Initialize(this, a1);
    if ( v5 < 0 )
    {
      CGenericUSB::~CGenericUSB(this);
    }
    else
    {
      v5 = 0;
      *a3 = this;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140001270  mov     [rsp+arg_0], rbx
0x140001275  mov     [rsp+arg_8], rsi
0x14000127a  push    rdi
0x14000127b  sub     rsp, 20h
0x14000127f  mov     rsi, r8
0x140001282  mov     rbx, rdx
0x140001285  test    rdx, rdx
0x140001288  jz      short loc_1400012E7
0x14000128a  lea     rax, [rdx+40h]
0x14000128e  mov     qword ptr [rdx+18h], 0
0x140001296  mov     qword ptr [rdx+20h], 0
0x14000129e  mov     qword ptr [rdx+28h], 0
0x1400012a6  mov     qword ptr [rdx+30h], 0
0x1400012ae  mov     qword ptr [rdx+38h], 0
0x1400012b6  mov     qword ptr [rdx+50h], 0
0x1400012be  mov     rdx, rcx; struct WDFDEVICE__ *
0x1400012c1  mov     rcx, rbx; this
0x1400012c4  mov     [rax+8], rax
0x1400012c8  mov     [rax], rax
0x1400012cb  call    ?Initialize@CGenericUSB@@AEAAJPEAUWDFDEVICE__@@@Z; CGenericUSB::Initialize(WDFDEVICE__ *)
0x1400012d0  mov     edi, eax
0x1400012d2  test    eax, eax
0x1400012d4  js      short loc_1400012DD
0x1400012d6  xor     edi, edi
0x1400012d8  mov     [rsi], rbx
0x1400012db  jmp     short loc_1400012EC
0x1400012dd  mov     rcx, rbx; this
0x1400012e0  call    ??1CGenericUSB@@QEAA@XZ; CGenericUSB::~CGenericUSB(void)
0x1400012e5  jmp     short loc_1400012EC
0x1400012e7  mov     edi, 0C0000017h
0x1400012ec  mov     rbx, [rsp+28h+arg_0]
0x1400012f1  mov     eax, edi
0x1400012f3  mov     rsi, [rsp+28h+arg_8]
0x1400012f8  add     rsp, 20h
0x1400012fc  pop     rdi
0x1400012fd  retn
```
