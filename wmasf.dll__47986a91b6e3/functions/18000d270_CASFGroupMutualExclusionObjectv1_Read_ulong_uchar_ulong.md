# CASFGroupMutualExclusionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000d270`
- end: `0x18000d4ba`
- name: `?Read@CASFGroupMutualExclusionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `586`
- prototype: `__int64 __fastcall(CASFGroupMutualExclusionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000d270`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFGroupMutualExclusionObjectv1::Read(
        CASFGroupMutualExclusionObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  int v8; // ebx
  unsigned int v9; // ebx
  __int128 v10; // xmm0
  unsigned __int8 *v11; // r12
  int v12; // eax
  unsigned __int16 v13; // cx
  __int64 v14; // r14
  __int64 v15; // rbp
  unsigned __int16 i; // r14
  __int64 v17; // r8
  int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  GUID *v19; // rbp
  unsigned __int16 v21; // [rsp+30h] [rbp-68h]
  _BYTE v22[8]; // [rsp+38h] [rbp-60h] BYREF
  GUID *v23; // [rsp+40h] [rbp-58h]
  __int64 v24; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 v25; // [rsp+50h] [rbp-48h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v22, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_26:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v22);
    return (unsigned int)v8;
  }
  if ( !a4 )
    goto LABEL_27;
  v9 = 42;
  if ( !(_DWORD)v4 )
    goto LABEL_24;
  if ( !a3 )
  {
LABEL_27:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v22);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x2A )
  {
LABEL_24:
    *a4 = 42;
LABEL_25:
    v8 = -1072887855;
    goto LABEL_26;
  }
  (*(void (__fastcall **)(CASFGroupMutualExclusionObjectv1 *))(*(_QWORD *)this + 216LL))(this);
  v10 = *(_OWORD *)a3;
  v23 = (GUID *)((char *)this + 48);
  v11 = a3 + 42;
  *((_OWORD *)this + 3) = v10;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  v12 = 0;
  *(_OWORD *)((char *)this + 696) = *(_OWORD *)(a3 + 24);
  v13 = *((_WORD *)a3 + 20);
  v21 = v13;
  while ( 1 )
  {
    LODWORD(v24) = v12;
    if ( (unsigned __int16)v12 >= v13 )
      break;
    v14 = v9 + 2;
    if ( v4 < (unsigned __int64)v9 + 2 )
    {
      *a4 = v14;
      goto LABEL_25;
    }
    v15 = *(unsigned __int16 *)v11;
    v25 = 0;
    v8 = (*(__int64 (__fastcall **)(CASFGroupMutualExclusionObjectv1 *, unsigned __int16 *))(*(_QWORD *)this + 128LL))(
           this,
           &v25);
    if ( v8 < 0 )
      goto LABEL_26;
    v9 = v14;
    if ( v4 < v14 + 2 * v15 )
    {
      *a4 = v14 + 2 * v15;
      goto LABEL_25;
    }
    v11 += 2;
    for ( i = 0; i < (unsigned __int16)v15; ++i )
    {
      v17 = *(unsigned __int16 *)v11;
      v9 += 2;
      v11 += 2;
      if ( (*(int (__fastcall **)(CASFGroupMutualExclusionObjectv1 *, _QWORD, __int64))(*(_QWORD *)this + 160LL))(
             this,
             v25,
             v17) < 0 )
        break;
    }
    HIWORD(v12) = WORD1(v24);
    v13 = v21;
    LOWORD(v12) = v24 + 1;
  }
  *a4 = v9;
  v18 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v18 && (v24 = 0, (**v18)(v18, &IID_IASFReadWriteTracker, &v24) >= 0) )
  {
    v19 = (GUID *)((char *)this + 48);
    (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v24 + 72LL))(
      v24,
      a3,
      *a4,
      (char *)this + 48);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  else
  {
    v19 = v23;
  }
  *v19 = CLSID_ASFMutualExclusionObject;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v22);
  return 0;
}

```

## disassembly

```asm
0x18000d270  mov     [rsp+arg_8], rbx
0x18000d275  push    rbp
0x18000d276  push    rsi
0x18000d277  push    rdi
0x18000d278  push    r12
0x18000d27a  push    r13
0x18000d27c  push    r14
0x18000d27e  push    r15
0x18000d280  sub     rsp, 60h
0x18000d284  mov     rax, cs:__security_cookie
0x18000d28b  xor     rax, rsp
0x18000d28e  mov     [rsp+98h+var_40], rax
0x18000d293  mov     r15d, edx
0x18000d296  mov     rsi, rcx
0x18000d299  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000d29d  mov     rdi, r9
0x18000d2a0  lea     rcx, [rsp+98h+var_60]; this
0x18000d2a5  mov     r13, r8
0x18000d2a8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000d2ad  cmp     qword ptr [rsi+28h], 0
0x18000d2b2  jnz     short loc_18000D2BE
0x18000d2b4  mov     ebx, 0C00D07F6h
0x18000d2b9  jmp     loc_18000D478
0x18000d2be  test    rdi, rdi
0x18000d2c1  jz      loc_18000D486
0x18000d2c7  mov     ebx, 2Ah ; '*'
0x18000d2cc  test    r15d, r15d
0x18000d2cf  jz      loc_18000D471
0x18000d2d5  test    r13, r13
0x18000d2d8  jz      loc_18000D486
0x18000d2de  cmp     r15d, ebx
0x18000d2e1  jb      loc_18000D471
0x18000d2e7  mov     rax, [rsi]
0x18000d2ea  mov     rcx, rsi
0x18000d2ed  mov     rax, [rax+0D8h]
0x18000d2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f9  movups  xmm0, xmmword ptr [r13+0]
0x18000d2fe  lea     rbp, [rsi+30h]
0x18000d302  mov     [rsp+98h+var_58], rbp
0x18000d307  lea     r12, [r13+2Ah]
0x18000d30b  movdqu  xmmword ptr [rbp+0], xmm0
0x18000d310  mov     rax, [r13+10h]
0x18000d314  mov     [rsi+40h], rax
0x18000d318  xor     eax, eax
0x18000d31a  movups  xmm0, xmmword ptr [r13+18h]
0x18000d31f  movdqu  xmmword ptr [rsi+2B8h], xmm0
0x18000d327  movzx   ecx, word ptr [r13+28h]
0x18000d32c  mov     [rsp+98h+var_68], cx
0x18000d331  mov     dword ptr [rsp+98h+var_50], eax
0x18000d335  cmp     ax, cx
0x18000d338  jnb     loc_18000D3ED
0x18000d33e  mov     eax, ebx
0x18000d340  lea     r14d, [rbx+2]
0x18000d344  add     rax, 2
0x18000d348  cmp     r15, rax
0x18000d34b  jb      loc_18000D3E5
0x18000d351  movzx   ebp, word ptr [r12]
0x18000d356  lea     rdx, [rsp+98h+var_48]
0x18000d35b  xor     eax, eax
0x18000d35d  mov     rcx, rsi
0x18000d360  mov     [rsp+98h+var_48], ax
0x18000d365  mov     rax, [rsi]
0x18000d368  mov     rax, [rax+80h]
0x18000d36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d374  mov     ebx, eax
0x18000d376  test    eax, eax
0x18000d378  js      loc_18000D478
0x18000d37e  lea     rcx, [r14+rbp*2]
0x18000d382  mov     ebx, r14d
0x18000d385  cmp     r15, rcx
0x18000d388  jb      short loc_18000D3DA
0x18000d38a  add     r12, 2
0x18000d38e  xor     r14d, r14d
0x18000d391  xor     eax, eax
0x18000d393  cmp     ax, bp
0x18000d396  jnb     short loc_18000D3C9
0x18000d398  mov     rax, [rsi]
0x18000d39b  mov     rcx, rsi
0x18000d39e  movzx   r8d, word ptr [r12]
0x18000d3a3  add     ebx, 2
0x18000d3a6  movzx   edx, [rsp+98h+var_48]
0x18000d3ab  add     r12, 2
0x18000d3af  mov     rax, [rax+0A0h]
0x18000d3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bb  test    eax, eax
0x18000d3bd  js      short loc_18000D3C9
0x18000d3bf  inc     r14w
0x18000d3c3  cmp     r14w, bp
0x18000d3c7  jb      short loc_18000D398
0x18000d3c9  mov     eax, dword ptr [rsp+98h+var_50]
0x18000d3cd  movzx   ecx, [rsp+98h+var_68]
0x18000d3d2  inc     ax
0x18000d3d5  jmp     loc_18000D331
0x18000d3da  lea     ecx, [r14+rbp*2]
0x18000d3de  mov     [rdi], ecx
0x18000d3e0  jmp     loc_18000D473
0x18000d3e5  mov     [rdi], r14d
0x18000d3e8  jmp     loc_18000D473
0x18000d3ed  mov     [rdi], ebx
0x18000d3ef  mov     rcx, [rsi+28h]
0x18000d3f3  test    rcx, rcx
0x18000d3f6  jz      short loc_18000D452
0x18000d3f8  mov     [rsp+98h+var_50], 0
0x18000d401  lea     r8, [rsp+98h+var_50]
0x18000d406  mov     rax, [rcx]
0x18000d409  lea     rdx, IID_IASFReadWriteTracker
0x18000d410  mov     rax, [rax]
0x18000d413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d418  test    eax, eax
0x18000d41a  js      short loc_18000D452
0x18000d41c  mov     rcx, [rsp+98h+var_50]
0x18000d421  lea     rbp, [rsi+30h]
0x18000d425  mov     r8d, [rdi]
0x18000d428  mov     r9, rbp
0x18000d42b  mov     rdx, r13
0x18000d42e  mov     rax, [rcx]
0x18000d431  mov     rax, [rax+48h]
0x18000d435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d43a  mov     rcx, [rsp+98h+var_50]
0x18000d43f  test    rcx, rcx
0x18000d442  jz      short loc_18000D457
0x18000d444  mov     rax, [rcx]
0x18000d447  mov     rax, [rax+10h]
0x18000d44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d450  jmp     short loc_18000D457
0x18000d452  mov     rbp, [rsp+98h+var_58]
0x18000d457  movups  xmm0, xmmword ptr cs:CLSID_ASFMutualExclusionObject.Data1
0x18000d45e  lea     rcx, [rsp+98h+var_60]; this
0x18000d463  movdqu  xmmword ptr [rbp+0], xmm0
0x18000d468  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d46d  xor     eax, eax
0x18000d46f  jmp     short loc_18000D495
0x18000d471  mov     [rdi], ebx
0x18000d473  mov     ebx, 0C00D07D1h
0x18000d478  lea     rcx, [rsp+98h+var_60]; this
0x18000d47d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d482  mov     eax, ebx
0x18000d484  jmp     short loc_18000D495
0x18000d486  lea     rcx, [rsp+98h+var_60]; this
0x18000d48b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d490  mov     eax, 80070057h
0x18000d495  mov     rcx, [rsp+98h+var_40]
0x18000d49a  xor     rcx, rsp; StackCookie
0x18000d49d  call    __security_check_cookie
0x18000d4a2  mov     rbx, [rsp+98h+arg_8]
0x18000d4aa  add     rsp, 60h
0x18000d4ae  pop     r15
0x18000d4b0  pop     r14
0x18000d4b2  pop     r13
0x18000d4b4  pop     r12
0x18000d4b6  pop     rdi
0x18000d4b7  pop     rsi
0x18000d4b8  pop     rbp
0x18000d4b9  retn
```
