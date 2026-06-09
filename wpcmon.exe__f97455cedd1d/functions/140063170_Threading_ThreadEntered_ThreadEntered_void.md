# Threading::ThreadEntered::~ThreadEntered(void)

- ea: `0x140063170`
- end: `0x140063225`
- name: `??1ThreadEntered@Threading@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(Threading::ThreadEntered *__hidden this)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x140016944`
- `0x14001b070`
- `0x14002da34`
- `0x140059b84`
- `0x14006639c`
- `0x14008cfb4`
- `0x14008d840`
- `0x14009e1bc`
- `0x14009e484`
- `0x14009f92b`
- `0x1400a35f5`
- `0x1400a3b8b`
- `0x1400a63f7`

## callees

- `0x1400626b4`
- `0x140063170`
- `0x140064f60`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!ConvertFiberToThread` at `0x1400631d5`
- `KERNEL32!ConvertFiberToThread` at `0x1400631d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400631b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400631c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400631b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400631c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400631f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400631f2`

## pseudocode

```c
void __fastcall Threading::ThreadEntered::~ThreadEntered(Threading::ThreadEntered *this, __int64 a2, int a3)
{
  int v4; // r9d
  __int64 v5; // rdx
  char *v6; // rbx
  char *v7; // rcx
  Threading::ThreadEntered *v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 16);
  if ( v4
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
  {
    WPP_SF_DS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, a3, v4, (__int64)this);
  }
  if ( TlsGetValue(dword_140110068) == (char *)this + 72 )
  {
    if ( *((_BYTE *)TlsGetValue(dword_140110068) + 10) )
      ConvertFiberToThread();
    v8 = this;
    stdext::try_execute__lambda_44e58872765d3f65c41832ed1a0da78f___(&v8);
    TlsSetValue(dword_140110068, 0);
  }
  v6 = (char *)this + 88;
  v7 = (char *)*((_QWORD *)v6 + 7);
  if ( v7 )
  {
    LOBYTE(v5) = v7 != v6;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 32LL))(v7, v5);
    *((_QWORD *)v6 + 7) = 0;
  }
}

```

## disassembly

```asm
0x140063170  push    rbx
0x140063172  sub     rsp, 30h
0x140063176  mov     rbx, rcx
0x140063179  mov     r9d, [rcx+40h]
0x14006317d  test    r9d, r9d
0x140063180  jz      short loc_1400631AE
0x140063182  lea     rax, WPP_GLOBAL_Control
0x140063189  mov     rcx, cs:WPP_GLOBAL_Control
0x140063190  cmp     rcx, rax
0x140063193  jz      short loc_1400631AE
0x140063195  test    byte ptr [rcx+1Ch], 10h
0x140063199  jz      short loc_1400631AE
0x14006319b  mov     edx, 14h
0x1400631a0  mov     [rsp+38h+var_18], rbx
0x1400631a5  mov     rcx, [rcx+10h]
0x1400631a9  call    WPP_SF_DS
0x1400631ae  mov     ecx, cs:dword_140110068; dwTlsIndex
0x1400631b4  call    cs:__imp_TlsGetValue
0x1400631ba  lea     rcx, [rbx+48h]
0x1400631be  cmp     rax, rcx
0x1400631c1  jnz     short loc_1400631F8
0x1400631c3  mov     ecx, cs:dword_140110068; dwTlsIndex
0x1400631c9  call    cs:__imp_TlsGetValue
0x1400631cf  cmp     byte ptr [rax+0Ah], 0
0x1400631d3  jz      short loc_1400631DB
0x1400631d5  call    cs:__imp_ConvertFiberToThread
0x1400631db  mov     [rsp+38h+arg_0], rbx
0x1400631e0  lea     rcx, [rsp+38h+arg_0]
0x1400631e5  call    stdext__try_execute__lambda_44e58872765d3f65c41832ed1a0da78f___
0x1400631ea  xor     edx, edx; lpTlsValue
0x1400631ec  mov     ecx, cs:dword_140110068; dwTlsIndex
0x1400631f2  call    cs:__imp_TlsSetValue
0x1400631f8  add     rbx, 58h ; 'X'
0x1400631fc  mov     rcx, [rbx+38h]
0x140063200  test    rcx, rcx
0x140063203  jz      short loc_14006321F
0x140063205  mov     rax, [rcx]
0x140063208  cmp     rcx, rbx
0x14006320b  setnz   dl
0x14006320e  mov     rax, [rax+20h]
0x140063212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063217  mov     qword ptr [rbx+38h], 0
0x14006321f  add     rsp, 30h
0x140063223  pop     rbx
0x140063224  retn
```
