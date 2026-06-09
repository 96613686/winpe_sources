# CASFCodecListObjectv1::Write(ulong,uchar *,ulong *)

- ea: `0x18001c5d0`
- end: `0x18001c6c4`
- name: `?Write@CASFCodecListObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(CASFCodecListObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18001c5d0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFCodecListObjectv1::Write(
        struct IWMSCriticalSection **this,
        int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v9; // ebx
  struct IWMSCriticalSection *v10; // rcx
  char v11[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v11, this[4]);
  if ( this[5] )
  {
    if ( a4 && (!a2 || a3) )
    {
      v9 = 0;
      *a4 = 0;
      v10 = this[5];
      if ( v10 )
      {
        v12 = 0;
        v9 = (**(__int64 (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v10)(
               v10,
               &IID_IASFReadWriteTracker,
               &v12);
        if ( v9 >= 0 )
        {
          (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v12 + 80LL))(
            v12,
            a3,
            *a4,
            (char *)this + 48);
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
      return (unsigned int)v9;
    }
    else
    {
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
      return 2147942487LL;
    }
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
    return 3222079478LL;
  }
}

```

## disassembly

```asm
0x18001c5d0  mov     [rsp+arg_8], rbx
0x18001c5d5  push    rbp
0x18001c5d6  push    rsi
0x18001c5d7  push    rdi
0x18001c5d8  sub     rsp, 50h
0x18001c5dc  mov     rax, cs:__security_cookie
0x18001c5e3  xor     rax, rsp
0x18001c5e6  mov     [rsp+68h+var_28], rax
0x18001c5eb  mov     ebx, edx
0x18001c5ed  mov     rsi, rcx
0x18001c5f0  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001c5f4  mov     rdi, r9
0x18001c5f7  lea     rcx, [rsp+68h+var_38]; this
0x18001c5fc  mov     rbp, r8
0x18001c5ff  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001c604  cmp     qword ptr [rsi+28h], 0
0x18001c609  jnz     short loc_18001C61F
0x18001c60b  lea     rcx, [rsp+68h+var_38]; this
0x18001c610  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c615  mov     eax, 0C00D07F6h
0x18001c61a  jmp     loc_18001C6AA
0x18001c61f  test    rdi, rdi
0x18001c622  jz      short loc_18001C69B
0x18001c624  test    ebx, ebx
0x18001c626  jz      short loc_18001C62D
0x18001c628  test    rbp, rbp
0x18001c62b  jz      short loc_18001C69B
0x18001c62d  xor     ebx, ebx
0x18001c62f  mov     [rdi], ebx
0x18001c631  mov     rcx, [rsi+28h]
0x18001c635  test    rcx, rcx
0x18001c638  jz      short loc_18001C68D
0x18001c63a  mov     [rsp+68h+var_30], rbx
0x18001c63f  lea     r8, [rsp+68h+var_30]
0x18001c644  mov     rax, [rcx]
0x18001c647  lea     rdx, IID_IASFReadWriteTracker
0x18001c64e  mov     rax, [rax]
0x18001c651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c656  mov     ebx, eax
0x18001c658  test    eax, eax
0x18001c65a  js      short loc_18001C68D
0x18001c65c  mov     rcx, [rsp+68h+var_30]
0x18001c661  lea     r9, [rsi+30h]
0x18001c665  mov     r8d, [rdi]
0x18001c668  mov     rdx, rbp
0x18001c66b  mov     r10, [rcx]
0x18001c66e  mov     rax, [r10+50h]
0x18001c672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c677  mov     rcx, [rsp+68h+var_30]
0x18001c67c  test    rcx, rcx
0x18001c67f  jz      short loc_18001C68D
0x18001c681  mov     rax, [rcx]
0x18001c684  mov     rax, [rax+10h]
0x18001c688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c68d  lea     rcx, [rsp+68h+var_38]; this
0x18001c692  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c697  mov     eax, ebx
0x18001c699  jmp     short loc_18001C6AA
0x18001c69b  lea     rcx, [rsp+68h+var_38]; this
0x18001c6a0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c6a5  mov     eax, 80070057h
0x18001c6aa  mov     rcx, [rsp+68h+var_28]
0x18001c6af  xor     rcx, rsp; StackCookie
0x18001c6b2  call    __security_check_cookie
0x18001c6b7  mov     rbx, [rsp+68h+arg_8]
0x18001c6bc  add     rsp, 50h
0x18001c6c0  pop     rdi
0x18001c6c1  pop     rsi
0x18001c6c2  pop     rbp
0x18001c6c3  retn
```
