# CASFMutualExclusionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000d700`
- end: `0x18000d903`
- name: `?Read@CASFMutualExclusionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `515`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000d700`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectv1::Read(
        CASFMutualExclusionObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  int v8; // ebx
  unsigned int v9; // edi
  __int128 v10; // xmm0
  __int64 v11; // r13
  unsigned __int8 *v12; // r12
  unsigned __int16 i; // r15
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  GUID *v15; // rbx
  _BYTE v17[8]; // [rsp+30h] [rbp-68h] BYREF
  GUID *v18; // [rsp+38h] [rbp-60h]
  __int64 v19; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 v20; // [rsp+48h] [rbp-50h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v17, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
    return (unsigned int)v8;
  }
  if ( !a4 )
    goto LABEL_23;
  v9 = 42;
  if ( !(_DWORD)v4 )
  {
LABEL_20:
    *a4 = 42;
    goto LABEL_21;
  }
  if ( !a3 )
  {
LABEL_23:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x2A )
    goto LABEL_20;
  (*(void (__fastcall **)(CASFMutualExclusionObjectv1 *))(*(_QWORD *)this + 216LL))(this);
  v10 = *(_OWORD *)a3;
  v18 = (GUID *)((char *)this + 48);
  *((_OWORD *)this + 3) = v10;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  *(_OWORD *)((char *)this + 696) = *(_OWORD *)(a3 + 24);
  v11 = *((unsigned __int16 *)a3 + 20);
  if ( v4 < 2 * v11 + 42 )
  {
    *a4 = 2 * v11 + 42;
LABEL_21:
    v8 = -1072887855;
    goto LABEL_22;
  }
  v12 = a3 + 42;
  for ( i = 0; i < (unsigned __int16)v11; ++i )
  {
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(CASFMutualExclusionObjectv1 *, unsigned __int16 *))(*(_QWORD *)this + 128LL))(
           this,
           &v20);
    if ( v8 < 0 )
      goto LABEL_22;
    v8 = (*(__int64 (__fastcall **)(CASFMutualExclusionObjectv1 *, _QWORD, _QWORD))(*(_QWORD *)this + 160LL))(
           this,
           v20,
           *(unsigned __int16 *)v12);
    if ( v8 < 0 )
      goto LABEL_22;
    v12 += 2;
    v9 += 2;
  }
  *a4 = v9;
  v14 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v14 && (v19 = 0, (**v14)(v14, &IID_IASFReadWriteTracker, &v19) >= 0) )
  {
    v15 = (GUID *)((char *)this + 48);
    (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v19 + 72LL))(
      v19,
      a3,
      *a4,
      (char *)this + 48);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  else
  {
    v15 = v18;
  }
  *v15 = CLSID_ASFMutualExclusionObject;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
  return 0;
}

```

## disassembly

```asm
0x18000d700  mov     [rsp+arg_8], rbx
0x18000d705  push    rbp
0x18000d706  push    rsi
0x18000d707  push    rdi
0x18000d708  push    r12
0x18000d70a  push    r13
0x18000d70c  push    r14
0x18000d70e  push    r15
0x18000d710  sub     rsp, 60h
0x18000d714  mov     rax, cs:__security_cookie
0x18000d71b  xor     rax, rsp
0x18000d71e  mov     [rsp+98h+var_48], rax
0x18000d723  mov     ebx, edx
0x18000d725  mov     rsi, rcx
0x18000d728  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000d72c  mov     r14, r9
0x18000d72f  lea     rcx, [rsp+98h+var_68]; this
0x18000d734  mov     rbp, r8
0x18000d737  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000d73c  cmp     qword ptr [rsi+28h], 0
0x18000d741  jnz     short loc_18000D74D
0x18000d743  mov     ebx, 0C00D07F6h
0x18000d748  jmp     loc_18000D8C1
0x18000d74d  test    r14, r14
0x18000d750  jz      loc_18000D8CF
0x18000d756  mov     edi, 2Ah ; '*'
0x18000d75b  test    ebx, ebx
0x18000d75d  jz      loc_18000D8B9
0x18000d763  test    rbp, rbp
0x18000d766  jz      loc_18000D8CF
0x18000d76c  cmp     ebx, edi
0x18000d76e  jb      loc_18000D8B9
0x18000d774  mov     rax, [rsi]
0x18000d777  mov     rcx, rsi
0x18000d77a  mov     rax, [rax+0D8h]
0x18000d781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d786  movups  xmm0, xmmword ptr [rbp+0]
0x18000d78a  lea     rax, [rsi+30h]
0x18000d78e  mov     [rsp+98h+var_60], rax
0x18000d793  movdqu  xmmword ptr [rax], xmm0
0x18000d797  mov     rax, [rbp+10h]
0x18000d79b  mov     [rsi+40h], rax
0x18000d79f  movups  xmm0, xmmword ptr [rbp+18h]
0x18000d7a3  movdqu  xmmword ptr [rsi+2B8h], xmm0
0x18000d7ab  movzx   r13d, word ptr [rbp+28h]
0x18000d7b0  lea     rcx, ds:2Ah[r13*2]
0x18000d7b8  cmp     rbx, rcx
0x18000d7bb  jnb     short loc_18000D7CD
0x18000d7bd  lea     eax, ds:2Ah[r13*2]
0x18000d7c5  mov     [r14], eax
0x18000d7c8  jmp     loc_18000D8BC
0x18000d7cd  lea     r12, [rbp+2Ah]
0x18000d7d1  xor     r15d, r15d
0x18000d7d4  cmp     r15w, r13w
0x18000d7d8  jnb     short loc_18000D835
0x18000d7da  xor     eax, eax
0x18000d7dc  lea     rdx, [rsp+98h+var_50]
0x18000d7e1  mov     [rsp+98h+var_50], ax
0x18000d7e6  mov     rcx, rsi
0x18000d7e9  mov     rax, [rsi]
0x18000d7ec  mov     rax, [rax+80h]
0x18000d7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7f8  mov     ebx, eax
0x18000d7fa  test    eax, eax
0x18000d7fc  js      loc_18000D8C1
0x18000d802  mov     rax, [rsi]
0x18000d805  mov     rcx, rsi
0x18000d808  movzx   r8d, word ptr [r12]
0x18000d80d  movzx   edx, [rsp+98h+var_50]
0x18000d812  mov     rax, [rax+0A0h]
0x18000d819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d81e  mov     ebx, eax
0x18000d820  test    eax, eax
0x18000d822  js      loc_18000D8C1
0x18000d828  add     r12, 2
0x18000d82c  add     edi, 2
0x18000d82f  inc     r15w
0x18000d833  jmp     short loc_18000D7D4
0x18000d835  mov     [r14], edi
0x18000d838  mov     rcx, [rsi+28h]
0x18000d83c  test    rcx, rcx
0x18000d83f  jz      short loc_18000D89B
0x18000d841  mov     [rsp+98h+var_58], 0
0x18000d84a  lea     r8, [rsp+98h+var_58]
0x18000d84f  mov     rax, [rcx]
0x18000d852  lea     rdx, IID_IASFReadWriteTracker
0x18000d859  mov     rax, [rax]
0x18000d85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d861  test    eax, eax
0x18000d863  js      short loc_18000D89B
0x18000d865  mov     rcx, [rsp+98h+var_58]
0x18000d86a  lea     rbx, [rsi+30h]
0x18000d86e  mov     r8d, [r14]
0x18000d871  mov     r9, rbx
0x18000d874  mov     rdx, rbp
0x18000d877  mov     rax, [rcx]
0x18000d87a  mov     rax, [rax+48h]
0x18000d87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d883  mov     rcx, [rsp+98h+var_58]
0x18000d888  test    rcx, rcx
0x18000d88b  jz      short loc_18000D8A0
0x18000d88d  mov     rax, [rcx]
0x18000d890  mov     rax, [rax+10h]
0x18000d894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d899  jmp     short loc_18000D8A0
0x18000d89b  mov     rbx, [rsp+98h+var_60]
0x18000d8a0  movups  xmm0, xmmword ptr cs:CLSID_ASFMutualExclusionObject.Data1
0x18000d8a7  lea     rcx, [rsp+98h+var_68]; this
0x18000d8ac  movdqu  xmmword ptr [rbx], xmm0
0x18000d8b0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d8b5  xor     eax, eax
0x18000d8b7  jmp     short loc_18000D8DE
0x18000d8b9  mov     [r14], edi
0x18000d8bc  mov     ebx, 0C00D07D1h
0x18000d8c1  lea     rcx, [rsp+98h+var_68]; this
0x18000d8c6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d8cb  mov     eax, ebx
0x18000d8cd  jmp     short loc_18000D8DE
0x18000d8cf  lea     rcx, [rsp+98h+var_68]; this
0x18000d8d4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000d8d9  mov     eax, 80070057h
0x18000d8de  mov     rcx, [rsp+98h+var_48]
0x18000d8e3  xor     rcx, rsp; StackCookie
0x18000d8e6  call    __security_check_cookie
0x18000d8eb  mov     rbx, [rsp+98h+arg_8]
0x18000d8f3  add     rsp, 60h
0x18000d8f7  pop     r15
0x18000d8f9  pop     r14
0x18000d8fb  pop     r13
0x18000d8fd  pop     r12
0x18000d8ff  pop     rdi
0x18000d900  pop     rsi
0x18000d901  pop     rbp
0x18000d902  retn
```
