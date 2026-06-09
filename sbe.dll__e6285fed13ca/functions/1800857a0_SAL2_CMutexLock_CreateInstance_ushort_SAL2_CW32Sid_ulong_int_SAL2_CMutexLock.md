# SAL2::CMutexLock::CreateInstance(ushort *,SAL2::CW32Sid *,ulong,int,SAL2::CMutexLock * *)

- ea: `0x1800857a0`
- end: `0x180085956`
- name: `?CreateInstance@CMutexLock@SAL2@@SAJPEAGPEAVCW32Sid@2@KHPEAPEAV12@@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct SAL2::CW32Sid *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct CMutexLock **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008035c`
- `0x180081d20`
- `0x180083c50`
- `0x18008573c`

## callees

- `0x1800017a0`
- `0x180080b28`
- `0x1800812f8`
- `0x180084cfc`
- `0x18008530c`
- `0x1800857a0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180085836`
- `KERNEL32!GetLastError` at `0x180085879`
- `KERNEL32!GetLastError` at `0x180085836`
- `KERNEL32!GetLastError` at `0x180085879`
- `KERNEL32!OpenMutexW` at `0x180085894`
- `KERNEL32!OpenMutexW` at `0x180085894`
- `KERNEL32!CreateMutexW` at `0x180085824`
- `KERNEL32!CreateMutexW` at `0x180085824`

## pseudocode

```c
__int64 __fastcall SAL2::CMutexLock::CreateInstance(
        unsigned __int16 *a1,
        struct SAL2::CW32Sid *a2,
        enum _ACCESS_MODE a3,
        __int64 a4,
        struct CMutexLock **a5)
{
  void *v7; // r8
  unsigned int v8; // ebx
  bool v9; // cc
  HANDLE v10; // rsi
  signed int LastError; // eax
  bool v12; // cc
  SAL2::CMutexLock *v13; // rax
  int v14; // r9d
  volatile signed __int32 *v15; // rax
  HANDLE v17[2]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v18[48]; // [rsp+40h] [rbp-40h] BYREF
  LPSECURITY_ATTRIBUTES lpMutexAttributes; // [rsp+70h] [rbp-10h]
  unsigned int v20; // [rsp+B8h] [rbp+38h] BYREF

  v17[0] = 0;
  v20 = 0;
  SAL2::CSALSecurityObject::CSALSecurityObject((SAL2::CSALSecurityObject *)v18, a2, a3, 0x100001u, &v20);
  v8 = v20;
  v9 = (int)v20 <= 0;
  if ( !v20 )
  {
    if ( ((a3 - 1) & 0xFFFFFFFC) != 0 || a3 == SET_ACCESS )
    {
      v8 = -2147024809;
      goto LABEL_30;
    }
    v17[0] = CreateMutexW(lpMutexAttributes, 0, a1);
    v10 = v17[0];
    if ( v17[0] )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( a3 == GRANT_ACCESS )
      {
        if ( LastError == 183 )
        {
          v8 = -2147024713;
          goto LABEL_30;
        }
        goto LABEL_20;
      }
      if ( a3 == DENY_ACCESS && LastError != 183 )
      {
        v12 = LastError <= 0;
        if ( !LastError )
        {
          v8 = -2147023728;
          goto LABEL_30;
        }
        goto LABEL_14;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( a3 == GRANT_ACCESS )
      {
        v12 = LastError <= 0;
LABEL_14:
        if ( v12 )
          goto LABEL_30;
        v8 = (unsigned __int16)LastError;
        goto LABEL_4;
      }
      v17[0] = OpenMutexW(0x100001u, 0, a1);
      v10 = v17[0];
      if ( !v17[0] )
      {
        v9 = (int)v8 <= 0;
        goto LABEL_2;
      }
    }
LABEL_20:
    v20 = 0;
    v13 = (SAL2::CMutexLock *)operator new(0x258u);
    if ( v13 && (v15 = (volatile signed __int32 *)SAL2::CMutexLock::CMutexLock(v13, a1, v10, v14, &v20)) != 0 )
    {
      v8 = v20;
      if ( v20 )
      {
        if ( (int)v20 > 0 )
          v8 = (unsigned __int16)v20 | 0x80070000;
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v15)(v15, 1);
      }
      else
      {
        v8 = 0;
        *a5 = (struct CMutexLock *)v15;
        _InterlockedIncrement(v15 + 2);
      }
    }
    else
    {
      v8 = -2147024882;
    }
    goto LABEL_30;
  }
LABEL_2:
  if ( !v9 )
  {
    v8 = (unsigned __int16)v8;
LABEL_4:
    v8 |= 0x80070000;
  }
LABEL_30:
  SAL2::CloseHandle((SAL2 *)v17, 0, v7);
  SAL2::CSALSecurityObject::~CSALSecurityObject((SAL2::CSALSecurityObject *)v18);
  return v8;
}

```

## disassembly

```asm
0x1800857a0  mov     r11, rsp
0x1800857a3  mov     [r11+8], rbx
0x1800857a7  mov     [r11+10h], rsi
0x1800857ab  mov     [r11+20h], r9d
0x1800857af  push    rbp
0x1800857b0  push    rdi
0x1800857b1  push    r14
0x1800857b3  mov     rbp, rsp
0x1800857b6  sub     rsp, 80h
0x1800857bd  mov     r14, rcx
0x1800857c0  mov     [rbp+var_50], 0
0x1800857c8  lea     rax, [rbp+arg_18]
0x1800857cc  mov     [rbp+arg_18], 0
0x1800857d3  lea     rcx, [rbp+var_40]; this
0x1800857d7  mov     [r11-78h], rax
0x1800857db  mov     r9d, 100001h; unsigned int
0x1800857e1  mov     edi, r8d
0x1800857e4  call    ??0CSALSecurityObject@SAL2@@QEAA@PEAVCW32Sid@1@W4_ACCESS_MODE@@KPEAK@Z; SAL2::CSALSecurityObject::CSALSecurityObject(SAL2::CW32Sid *,_ACCESS_MODE,ulong,ulong *)
0x1800857e9  mov     ebx, [rbp+arg_18]
0x1800857ec  test    ebx, ebx
0x1800857ee  jz      short loc_180085804
0x1800857f0  jle     loc_180085928
0x1800857f6  movzx   ebx, bx
0x1800857f9  or      ebx, 80070000h
0x1800857ff  jmp     loc_180085928
0x180085804  lea     eax, [rdi-1]
0x180085807  test    eax, 0FFFFFFFCh
0x18008580c  jnz     loc_180085923
0x180085812  cmp     edi, 2
0x180085815  jz      loc_180085923
0x18008581b  mov     rcx, [rbp+lpMutexAttributes]; lpMutexAttributes
0x18008581f  mov     r8, r14; lpName
0x180085822  xor     edx, edx; bInitialOwner
0x180085824  call    cs:__imp_CreateMutexW
0x18008582a  mov     [rbp+var_50], rax
0x18008582e  mov     rsi, rax
0x180085831  test    rax, rax
0x180085834  jz      short loc_180085879
0x180085836  call    cs:__imp_GetLastError
0x18008583c  mov     ebx, eax
0x18008583e  cmp     edi, 1
0x180085841  jnz     short loc_180085854
0x180085843  cmp     eax, 0B7h
0x180085848  jnz     short loc_1800858AD
0x18008584a  mov     ebx, 800700B7h
0x18008584f  jmp     loc_180085928
0x180085854  cmp     edi, 3
0x180085857  jnz     short loc_1800858AD
0x180085859  cmp     eax, 0B7h
0x18008585e  jz      short loc_1800858AD
0x180085860  test    eax, eax
0x180085862  jz      short loc_18008586F
0x180085864  jle     loc_180085928
0x18008586a  movzx   ebx, ax
0x18008586d  jmp     short loc_1800857F9
0x18008586f  mov     ebx, 80070490h
0x180085874  jmp     loc_180085928
0x180085879  call    cs:__imp_GetLastError
0x18008587f  mov     ebx, eax
0x180085881  cmp     edi, 1
0x180085884  jz      loc_18008591C
0x18008588a  mov     r8, r14; lpName
0x18008588d  xor     edx, edx; bInheritHandle
0x18008588f  mov     ecx, 100001h; dwDesiredAccess
0x180085894  call    cs:__imp_OpenMutexW
0x18008589a  mov     [rbp+var_50], rax
0x18008589e  mov     rsi, rax
0x1800858a1  test    rax, rax
0x1800858a4  jnz     short loc_1800858AD
0x1800858a6  test    ebx, ebx
0x1800858a8  jmp     loc_1800857F0
0x1800858ad  mov     ecx, 258h; Size
0x1800858b2  mov     [rbp+arg_18], 0
0x1800858b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800858be  test    rax, rax
0x1800858c1  jz      short loc_180085915
0x1800858c3  lea     rcx, [rbp+arg_18]
0x1800858c7  mov     r8, rsi; void *
0x1800858ca  mov     [rsp+80h+var_60], rcx; unsigned int *
0x1800858cf  mov     rdx, r14; unsigned __int16 *
0x1800858d2  mov     rcx, rax; this
0x1800858d5  call    ??0CMutexLock@SAL2@@AEAA@PEAGPEAXHPEAK@Z; SAL2::CMutexLock::CMutexLock(ushort *,void *,int,ulong *)
0x1800858da  mov     rcx, rax
0x1800858dd  test    rax, rax
0x1800858e0  jz      short loc_180085915
0x1800858e2  mov     ebx, [rbp+arg_18]
0x1800858e5  test    ebx, ebx
0x1800858e7  jz      short loc_180085906
0x1800858e9  jle     short loc_1800858F4
0x1800858eb  movzx   ebx, bx
0x1800858ee  or      ebx, 80070000h
0x1800858f4  mov     rax, [rax]
0x1800858f7  mov     edx, 1
0x1800858fc  mov     rax, [rax]
0x1800858ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085904  jmp     short loc_180085928
0x180085906  mov     rax, [rbp+arg_20]
0x18008590a  xor     ebx, ebx
0x18008590c  mov     [rax], rcx
0x18008590f  lock inc dword ptr [rcx+8]
0x180085913  jmp     short loc_180085928
0x180085915  mov     ebx, 8007000Eh
0x18008591a  jmp     short loc_180085928
0x18008591c  test    eax, eax
0x18008591e  jmp     loc_180085864
0x180085923  mov     ebx, 80070057h
0x180085928  xor     edx, edx; void **
0x18008592a  lea     rcx, [rbp+var_50]; this
0x18008592e  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x180085933  lea     rcx, [rbp+var_40]; this
0x180085937  call    ??1CSALSecurityObject@SAL2@@UEAA@XZ; SAL2::CSALSecurityObject::~CSALSecurityObject(void)
0x18008593c  lea     r11, [rsp+80h+var_s0]
0x180085944  mov     eax, ebx
0x180085946  mov     rbx, [r11+20h]
0x18008594a  mov     rsi, [r11+28h]
0x18008594e  mov     rsp, r11
0x180085951  pop     r14
0x180085953  pop     rdi
0x180085954  pop     rbp
0x180085955  retn
```
