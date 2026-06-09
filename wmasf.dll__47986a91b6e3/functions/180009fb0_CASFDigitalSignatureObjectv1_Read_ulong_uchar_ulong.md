# CASFDigitalSignatureObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180009fb0`
- end: `0x18000a14f`
- name: `?Read@CASFDigitalSignatureObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `415`
- prototype: `int(CASFDigitalSignatureObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x180009fb0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFDigitalSignatureObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int128 v10; // xmm0
  struct IWMSCriticalSection *v11; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // edx
  struct IWMSCriticalSection *v16; // rax
  struct IWMSCriticalSection *v17; // rcx
  char v18[8]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v19[2]; // [rsp+38h] [rbp-18h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v18, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_11:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return v8;
  }
  if ( !a4 )
    goto LABEL_24;
  v9 = 24;
  if ( !(_DWORD)v4 )
  {
LABEL_9:
    v8 = -1072887855;
LABEL_10:
    *a4 = v9;
    goto LABEL_11;
  }
  if ( !a3 )
  {
LABEL_24:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_9;
  v10 = *(_OWORD *)a3;
  v19[0] = 24;
  *((_OWORD *)this + 3) = v10;
  v11 = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  this[8] = v11;
  if ( v4 < (unsigned __int64)v11 )
  {
    v9 = (unsigned int)v11;
    goto LABEL_9;
  }
  v8 = -1072887855;
  if ( (unsigned int)CHECK_FOR_SPACE(v19, 8u, v4) == -1072887855 )
    goto LABEL_23;
  *((_DWORD *)this + 21) = *((_DWORD *)a3 + 6);
  v14 = *((_DWORD *)a3 + 7);
  *((_DWORD *)this + 24) = v14;
  if ( v14 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v19, v14, v13) != -1072887855 )
    {
      v16 = (struct IWMSCriticalSection *)operator new[](v15);
      this[11] = v16;
      if ( !v16 )
      {
        v8 = -2147024882;
        goto LABEL_11;
      }
      memcpy_0(v16, a3 + 32, *((unsigned int *)this + 24));
      goto LABEL_18;
    }
LABEL_23:
    v9 = v19[0];
    goto LABEL_10;
  }
LABEL_18:
  *a4 = v19[0];
  v17 = this[5];
  if ( v17 )
  {
    *(_QWORD *)v19 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, unsigned int *))v17)(
           v17,
           &IID_IASFReadWriteTracker,
           v19) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v19 + 72LL))(
        *(_QWORD *)v19,
        a3,
        *a4,
        (char *)this + 48);
      if ( *(_QWORD *)v19 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 16LL))(*(_QWORD *)v19);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
  return 0;
}

```

## disassembly

```asm
0x180009fb0  push    rbp
0x180009fb2  push    rbx
0x180009fb3  push    rsi
0x180009fb4  push    rdi
0x180009fb5  push    r12
0x180009fb7  push    r14
0x180009fb9  push    r15
0x180009fbb  mov     rbp, rsp
0x180009fbe  sub     rsp, 50h
0x180009fc2  mov     rax, cs:__security_cookie
0x180009fc9  xor     rax, rsp
0x180009fcc  mov     [rbp+var_10], rax
0x180009fd0  mov     r15d, edx
0x180009fd3  mov     rdi, rcx
0x180009fd6  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180009fda  mov     rsi, r9
0x180009fdd  lea     rcx, [rbp+var_20]; this
0x180009fe1  mov     r14, r8
0x180009fe4  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180009fe9  cmp     qword ptr [rdi+28h], 0
0x180009fee  jnz     short loc_180009FF7
0x180009ff0  mov     ebx, 0C00D07F6h
0x180009ff5  jmp     short loc_18000A03A
0x180009ff7  test    rsi, rsi
0x180009ffa  jz      loc_18000A126
0x18000a000  mov     eax, 18h
0x18000a005  test    r15d, r15d
0x18000a008  jz      short loc_18000A033
0x18000a00a  test    r14, r14
0x18000a00d  jz      loc_18000A126
0x18000a013  cmp     r15d, eax
0x18000a016  jb      short loc_18000A033
0x18000a018  movups  xmm0, xmmword ptr [r14]
0x18000a01c  mov     [rbp+var_18], eax
0x18000a01f  movdqu  xmmword ptr [rdi+30h], xmm0
0x18000a024  mov     rcx, [r14+10h]
0x18000a028  mov     [rdi+40h], rcx
0x18000a02c  cmp     r15, rcx
0x18000a02f  jnb     short loc_18000A04A
0x18000a031  mov     eax, ecx
0x18000a033  mov     ebx, 0C00D07D1h
0x18000a038  mov     [rsi], eax
0x18000a03a  lea     rcx, [rbp+var_20]; this
0x18000a03e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000a043  mov     eax, ebx
0x18000a045  jmp     loc_18000A134
0x18000a04a  mov     r8d, r15d; unsigned int
0x18000a04d  lea     rcx, [rbp+var_18]; unsigned int *
0x18000a051  mov     edx, 8; unsigned int
0x18000a056  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000a05b  mov     ebx, 0C00D07D1h
0x18000a060  cmp     eax, ebx
0x18000a062  jz      loc_18000A11E
0x18000a068  mov     eax, [r14+18h]
0x18000a06c  mov     [rdi+54h], eax
0x18000a06f  mov     edx, [r14+1Ch]; unsigned int
0x18000a073  mov     [rdi+60h], edx
0x18000a076  test    edx, edx
0x18000a078  jz      short loc_18000A0B2
0x18000a07a  lea     rcx, [rbp+var_18]; unsigned int *
0x18000a07e  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000a083  cmp     eax, ebx
0x18000a085  jz      loc_18000A11E
0x18000a08b  mov     ecx, edx; unsigned __int64
0x18000a08d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a092  mov     [rdi+58h], rax
0x18000a096  test    rax, rax
0x18000a099  jnz     short loc_18000A0A2
0x18000a09b  mov     ebx, 8007000Eh
0x18000a0a0  jmp     short loc_18000A03A
0x18000a0a2  mov     r8d, [rdi+60h]; Size
0x18000a0a6  lea     rdx, [r14+20h]; Src
0x18000a0aa  mov     rcx, rax; void *
0x18000a0ad  call    memcpy_0
0x18000a0b2  mov     eax, [rbp+var_18]
0x18000a0b5  mov     [rsi], eax
0x18000a0b7  mov     rcx, [rdi+28h]
0x18000a0bb  test    rcx, rcx
0x18000a0be  jz      short loc_18000A111
0x18000a0c0  mov     qword ptr [rbp+var_18], 0
0x18000a0c8  lea     r8, [rbp+var_18]
0x18000a0cc  mov     rax, [rcx]
0x18000a0cf  lea     rdx, IID_IASFReadWriteTracker
0x18000a0d6  mov     rax, [rax]
0x18000a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0de  test    eax, eax
0x18000a0e0  js      short loc_18000A111
0x18000a0e2  mov     rcx, qword ptr [rbp+var_18]
0x18000a0e6  lea     r9, [rdi+30h]
0x18000a0ea  mov     r8d, [rsi]
0x18000a0ed  mov     rdx, r14
0x18000a0f0  mov     rax, [rcx]
0x18000a0f3  mov     rax, [rax+48h]
0x18000a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fc  mov     rcx, qword ptr [rbp+var_18]
0x18000a100  test    rcx, rcx
0x18000a103  jz      short loc_18000A111
0x18000a105  mov     rax, [rcx]
0x18000a108  mov     rax, [rax+10h]
0x18000a10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a111  lea     rcx, [rbp+var_20]; this
0x18000a115  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000a11a  xor     eax, eax
0x18000a11c  jmp     short loc_18000A134
0x18000a11e  mov     eax, [rbp+var_18]
0x18000a121  jmp     loc_18000A038
0x18000a126  lea     rcx, [rbp+var_20]; this
0x18000a12a  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000a12f  mov     eax, 80070057h
0x18000a134  mov     rcx, [rbp+var_10]
0x18000a138  xor     rcx, rsp; StackCookie
0x18000a13b  call    __security_check_cookie
0x18000a140  add     rsp, 50h
0x18000a144  pop     r15
0x18000a146  pop     r14
0x18000a148  pop     r12
0x18000a14a  pop     rdi
0x18000a14b  pop     rsi
0x18000a14c  pop     rbx
0x18000a14d  pop     rbp
0x18000a14e  retn
```
