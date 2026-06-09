# CTask::~CTask(void)

- ea: `0x18001fe78`
- end: `0x1800200f1`
- name: `??1CTask@@QEAA@XZ`
- size: `633`
- prototype: `void __fastcall(CTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e180`

## callees

- `0x18001fe78`
- `0x1800200f8`
- `0x180020140`
- `0x180031b30`
- `0x180032198`
- `0x1800329db`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002007d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800200a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800200cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002007d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800200a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800200cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ffbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ffbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff27`

## pseudocode

```c
void __fastcall CTask::~CTask(CTask *this, int *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  HMODULE v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  *((_DWORD *)this + 1) = 1;
  v3 = *((_QWORD *)this + 33);
  if ( v3 )
  {
    if ( (*((_BYTE *)this + 112) & 0x40) != 0 )
    {
      *((_DWORD *)this + 24) = 0;
      *((_DWORD *)this + 25) = 0;
      *((_QWORD *)this + 13) = 0;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 40LL))(v3, 7);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 16LL))(*((_QWORD *)this + 33));
  }
  if ( *((_DWORD *)this + 254) )
    CPXWizardSemaphoreLock::Release((CTask *)((char *)this + 976), a2, 0);
  if ( *((_QWORD *)this + 42) != *((_QWORD *)this + 43) )
    CTask::ClearProcessedStack(this);
  if ( *((_QWORD *)this + 39) != *((_QWORD *)this + 40) )
    CTask::ClearParsingStack(this);
  if ( *((_DWORD *)this + 108) )
  {
    CoTaskMemFree(*((LPVOID *)this + 55));
    *((_QWORD *)this + 55) = 0;
  }
  v4 = *((_QWORD *)this + 121);
  if ( v4 || *((_QWORD *)this + 55) )
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 88LL))(
      *((_QWORD *)this + 36),
      v4,
      *((_QWORD *)this + 55),
      *((unsigned int *)this + 30));
  v5 = *((_QWORD *)this + 36);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 37);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 38);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (HMODULE)*((_QWORD *)this + 129);
  if ( v8 )
    FreeLibrary(v8);
  v9 = *((_QWORD *)this + 31);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 32);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *((_QWORD *)this + 34);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = *((_QWORD *)this + 35);
  if ( v12
    && _RTDynamicCast_0(
         v12,
         0,
         &IXWizardSource `RTTI Type Descriptor',
         &IPXWizardInternalSource `RTTI Type Descriptor',
         0) )
  {
    v13 = _RTDynamicCast_0(
            *((_QWORD *)this + 35),
            0,
            &IXWizardSource `RTTI Type Descriptor',
            &IPXWizardInternalSource `RTTI Type Descriptor',
            0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
  }
  CPXWizardSemaphoreLock::~CPXWizardSemaphoreLock((CTask *)((char *)this + 976));
  v14 = (void *)*((_QWORD *)this + 45);
  if ( v14 )
  {
    operator delete(v14);
    *((_QWORD *)this + 45) = 0;
    *((_QWORD *)this + 46) = 0;
    *((_QWORD *)this + 47) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 42);
  if ( v15 )
  {
    operator delete(v15);
    *((_QWORD *)this + 42) = 0;
    *((_QWORD *)this + 43) = 0;
    *((_QWORD *)this + 44) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 39);
  if ( v16 )
  {
    operator delete(v16);
    *((_QWORD *)this + 39) = 0;
    *((_QWORD *)this + 40) = 0;
    *((_QWORD *)this + 41) = 0;
  }
}

```

## disassembly

```asm
0x18001fe78  mov     [rsp+arg_0], rbx
0x18001fe7d  push    rdi
0x18001fe7e  sub     rsp, 30h
0x18001fe82  mov     rbx, rcx
0x18001fe85  mov     dword ptr [rcx+4], 1
0x18001fe8c  mov     rcx, [rcx+108h]
0x18001fe93  xor     edi, edi
0x18001fe95  test    rcx, rcx
0x18001fe98  jz      short loc_18001FED1
0x18001fe9a  test    byte ptr [rbx+70h], 40h
0x18001fe9e  jz      short loc_18001FEBE
0x18001fea0  lea     r8, [rbx+28h]
0x18001fea4  mov     [r8+38h], edi
0x18001fea8  mov     [rbx+64h], edi
0x18001feab  mov     [rbx+68h], rdi
0x18001feaf  mov     rax, [rcx]
0x18001feb2  lea     edx, [rdi+7]
0x18001feb5  mov     rax, [rax+28h]
0x18001feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001febe  mov     rcx, [rbx+108h]
0x18001fec5  mov     rax, [rcx]
0x18001fec8  mov     rax, [rax+10h]
0x18001fecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed1  cmp     [rbx+3F8h], edi
0x18001fed7  jz      short loc_18001FEE8
0x18001fed9  lea     rcx, [rbx+3D0h]; this
0x18001fee0  xor     r8d, r8d; int
0x18001fee3  call    ?Release@CPXWizardSemaphoreLock@@QEAAJPEAJH@Z; CPXWizardSemaphoreLock::Release(long *,int)
0x18001fee8  mov     rax, [rbx+158h]
0x18001feef  cmp     [rbx+150h], rax
0x18001fef6  jz      short loc_18001FF00
0x18001fef8  mov     rcx, rbx; this
0x18001fefb  call    ?ClearProcessedStack@CTask@@AEAAXXZ; CTask::ClearProcessedStack(void)
0x18001ff00  mov     rax, [rbx+140h]
0x18001ff07  cmp     [rbx+138h], rax
0x18001ff0e  jz      short loc_18001FF18
0x18001ff10  mov     rcx, rbx; this
0x18001ff13  call    ?ClearParsingStack@CTask@@AEAAXXZ; CTask::ClearParsingStack(void)
0x18001ff18  cmp     [rbx+1B0h], edi
0x18001ff1e  jz      short loc_18001FF34
0x18001ff20  mov     rcx, [rbx+1B8h]; pv
0x18001ff27  call    cs:__imp_CoTaskMemFree
0x18001ff2d  mov     [rbx+1B8h], rdi
0x18001ff34  mov     rdx, [rbx+3C8h]
0x18001ff3b  test    rdx, rdx
0x18001ff3e  jnz     short loc_18001FF49
0x18001ff40  cmp     [rbx+1B8h], rdi
0x18001ff47  jz      short loc_18001FF67
0x18001ff49  mov     rcx, [rbx+120h]
0x18001ff50  mov     rax, [rcx]
0x18001ff53  mov     r9d, [rbx+78h]
0x18001ff57  mov     r8, [rbx+1B8h]
0x18001ff5e  mov     rax, [rax+58h]
0x18001ff62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff67  mov     rcx, [rbx+120h]
0x18001ff6e  test    rcx, rcx
0x18001ff71  jz      short loc_18001FF7F
0x18001ff73  mov     rax, [rcx]
0x18001ff76  mov     rax, [rax+10h]
0x18001ff7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff7f  mov     rcx, [rbx+128h]
0x18001ff86  test    rcx, rcx
0x18001ff89  jz      short loc_18001FF97
0x18001ff8b  mov     rax, [rcx]
0x18001ff8e  mov     rax, [rax+10h]
0x18001ff92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff97  mov     rcx, [rbx+130h]
0x18001ff9e  test    rcx, rcx
0x18001ffa1  jz      short loc_18001FFAF
0x18001ffa3  mov     rax, [rcx]
0x18001ffa6  mov     rax, [rax+10h]
0x18001ffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffaf  mov     rcx, [rbx+408h]; hLibModule
0x18001ffb6  test    rcx, rcx
0x18001ffb9  jz      short loc_18001FFC1
0x18001ffbb  call    cs:__imp_FreeLibrary
0x18001ffc1  mov     rcx, [rbx+0F8h]
0x18001ffc8  test    rcx, rcx
0x18001ffcb  jz      short loc_18001FFD9
0x18001ffcd  mov     rax, [rcx]
0x18001ffd0  mov     rax, [rax+10h]
0x18001ffd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd9  mov     rcx, [rbx+100h]
0x18001ffe0  test    rcx, rcx
0x18001ffe3  jz      short loc_18001FFF1
0x18001ffe5  mov     rax, [rcx]
0x18001ffe8  mov     rax, [rax+10h]
0x18001ffec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fff1  mov     rcx, [rbx+110h]
0x18001fff8  test    rcx, rcx
0x18001fffb  jz      short loc_180020009
0x18001fffd  mov     rax, [rcx]
0x180020000  mov     rax, [rax+10h]
0x180020004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020009  mov     rcx, [rbx+118h]
0x180020010  test    rcx, rcx
0x180020013  jz      short loc_180020065
0x180020015  mov     [rsp+38h+var_18], edi
0x180020019  lea     r9, ??_R0?AUIPXWizardInternalSource@@@8; IPXWizardInternalSource `RTTI Type Descriptor'
0x180020020  lea     r8, ??_R0?AUIXWizardSource@@@8; IXWizardSource `RTTI Type Descriptor'
0x180020027  xor     edx, edx
0x180020029  call    __RTDynamicCast_0
0x18002002e  test    rax, rax
0x180020031  jz      short loc_180020065
0x180020033  mov     [rsp+38h+var_18], edi
0x180020037  lea     r9, ??_R0?AUIPXWizardInternalSource@@@8; IPXWizardInternalSource `RTTI Type Descriptor'
0x18002003e  lea     r8, ??_R0?AUIXWizardSource@@@8; IXWizardSource `RTTI Type Descriptor'
0x180020045  xor     edx, edx
0x180020047  mov     rcx, [rbx+118h]
0x18002004e  call    __RTDynamicCast_0
0x180020053  mov     rdx, rax
0x180020056  mov     rcx, [rax]
0x180020059  mov     rax, [rcx+20h]
0x18002005d  mov     rcx, rdx
0x180020060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020065  lea     rcx, [rbx+3D0h]; this
0x18002006c  call    ??1CPXWizardSemaphoreLock@@QEAA@XZ; CPXWizardSemaphoreLock::~CPXWizardSemaphoreLock(void)
0x180020071  mov     rcx, [rbx+168h]
0x180020078  test    rcx, rcx
0x18002007b  jz      short loc_180020098
0x18002007d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020083  mov     [rbx+168h], rdi
0x18002008a  mov     [rbx+170h], rdi
0x180020091  mov     [rbx+178h], rdi
0x180020098  mov     rcx, [rbx+150h]
0x18002009f  test    rcx, rcx
0x1800200a2  jz      short loc_1800200BF
0x1800200a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800200aa  mov     [rbx+150h], rdi
0x1800200b1  mov     [rbx+158h], rdi
0x1800200b8  mov     [rbx+160h], rdi
0x1800200bf  mov     rcx, [rbx+138h]
0x1800200c6  test    rcx, rcx
0x1800200c9  jz      short loc_1800200E6
0x1800200cb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800200d1  mov     [rbx+138h], rdi
0x1800200d8  mov     [rbx+140h], rdi
0x1800200df  mov     [rbx+148h], rdi
0x1800200e6  mov     rbx, [rsp+38h+arg_0]
0x1800200eb  add     rsp, 30h
0x1800200ef  pop     rdi
0x1800200f0  retn
```
