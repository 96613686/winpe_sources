# SBECoreUtil::CMutexLock::CreateInstance(ushort *,SBECoreUtil::CW32SID *,ulong,int,SBECoreUtil::CMutexLock * *)

- ea: `0x180060af8`
- end: `0x180060ca7`
- name: `?CreateInstance@CMutexLock@SBECoreUtil@@SAJPEAGPEAVCW32SID@2@KHPEAPEAV12@@Z`
- size: `431`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpName@<rcx>, struct SBECoreUtil::CW32SID *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct CMutexLock **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aeb28`
- `0x1800af400`

## callees

- `0x1800017a0`
- `0x18005ff10`
- `0x1800605d0`
- `0x180060af8`
- `0x180060cb0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180060bde`
- `KERNEL32!GetLastError` at `0x180060c10`
- `KERNEL32!GetLastError` at `0x180060c44`
- `KERNEL32!GetLastError` at `0x180060bde`
- `KERNEL32!GetLastError` at `0x180060c10`
- `KERNEL32!GetLastError` at `0x180060c44`
- `KERNEL32!OpenMutexW` at `0x180060c31`
- `KERNEL32!OpenMutexW` at `0x180060c31`
- `KERNEL32!CreateMutexW` at `0x180060bcb`
- `KERNEL32!CreateMutexW` at `0x180060bcb`

## pseudocode

```c
__int64 __fastcall SBECoreUtil::CMutexLock::CreateInstance(
        LPCWSTR lpName,
        struct SBECoreUtil::CW32SID *a2,
        void *a3,
        BOOL a4,
        struct CMutexLock **a5)
{
  unsigned int Instance; // ebx
  void (__fastcall ***v9)(_QWORD, __int64); // rdi
  SBECoreUtil::CSBESecurityObject *v10; // rax
  __int64 v11; // rax
  struct _SECURITY_ATTRIBUTES *v12; // rcx
  HANDLE v13; // rbp
  signed int LastError; // eax
  signed int v15; // eax
  enum _ACCESS_MODE v17; // [rsp+20h] [rbp-48h]
  HANDLE v18[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = 0;
  v18[0] = 0;
  if ( (((_DWORD)a3 - 1) & 0xFFFFFFFD) != 0 )
    goto LABEL_2;
  v9 = 0;
  if ( a4 )
  {
    if ( (_DWORD)a3 != 1 )
    {
LABEL_2:
      Instance = -2147024809;
      goto LABEL_27;
    }
    goto LABEL_7;
  }
  if ( (_DWORD)a3 == 1 )
  {
LABEL_7:
    if ( a2 )
    {
      v10 = (SBECoreUtil::CSBESecurityObject *)operator new(0x48u);
      if ( !v10
        || (v11 = SBECoreUtil::CSBESecurityObject::CSBESecurityObject(
                    v10,
                    a2,
                    (enum _ACCESS_MODE)a3,
                    0x1F0001u,
                    v17,
                    0x100000u,
                    &v19),
            (v9 = (void (__fastcall ***)(_QWORD, __int64))v11) == 0) )
      {
        Instance = -2147024882;
        goto LABEL_27;
      }
      Instance = v19;
      if ( v19 )
      {
        if ( (int)v19 > 0 )
          Instance = (unsigned __int16)v19 | 0x80070000;
        goto LABEL_26;
      }
      v12 = *(struct _SECURITY_ATTRIBUTES **)(v11 + 56);
    }
    else
    {
      v12 = 0;
    }
    v18[0] = CreateMutexW(v12, a4, lpName);
    v13 = v18[0];
    if ( !v18[0] )
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
LABEL_25:
      if ( !v9 )
        goto LABEL_27;
LABEL_26:
      (**v9)(v9, 1);
      goto LABEL_27;
    }
    if ( GetLastError() == 183 )
    {
      Instance = -2147024713;
      goto LABEL_25;
    }
LABEL_24:
    Instance = SBECoreUtil::CMutexLock::CreateInstance(v13, a4, a5);
    goto LABEL_25;
  }
  v18[0] = OpenMutexW(0x100000u, 0, lpName);
  v13 = v18[0];
  if ( v18[0] )
    goto LABEL_24;
  v15 = GetLastError();
  Instance = v15;
  if ( v15 > 0 )
    Instance = (unsigned __int16)v15 | 0x80070000;
LABEL_27:
  SBECoreUtil::CloseHandle((SBECoreUtil *)v18, (void **)a2, a3);
  return Instance;
}

```

## disassembly

```asm
0x180060af8  mov     rax, rsp
0x180060afb  mov     [rax+8], rbx
0x180060aff  mov     [rax+10h], rbp
0x180060b03  push    rsi
0x180060b04  push    rdi
0x180060b05  push    r14
0x180060b07  sub     rsp, 50h
0x180060b0b  mov     dword ptr [rax+18h], 0
0x180060b12  mov     r14d, r9d
0x180060b15  mov     qword ptr [rax-28h], 0
0x180060b1d  mov     esi, r8d
0x180060b20  lea     eax, [r8-1]
0x180060b24  mov     rbx, rdx
0x180060b27  mov     rbp, rcx
0x180060b2a  test    eax, 0FFFFFFFDh
0x180060b2f  jz      short loc_180060B3B
0x180060b31  mov     ebx, 80070057h
0x180060b36  jmp     loc_180060C88
0x180060b3b  xor     edi, edi
0x180060b3d  test    r14d, r14d
0x180060b40  jz      short loc_180060B49
0x180060b42  cmp     esi, 1
0x180060b45  jz      short loc_180060B52
0x180060b47  jmp     short loc_180060B31
0x180060b49  cmp     esi, 1
0x180060b4c  jnz     loc_180060C27
0x180060b52  test    rbx, rbx
0x180060b55  jz      short loc_180060BC3
0x180060b57  mov     ecx, 48h ; 'H'; Size
0x180060b5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060b61  test    rax, rax
0x180060b64  jz      short loc_180060BB9
0x180060b66  lea     rcx, [rsp+68h+arg_10]
0x180060b6e  mov     r9d, 1F0001h; unsigned int
0x180060b74  mov     [rsp+68h+var_38], rcx; unsigned int *
0x180060b79  mov     rdx, rbx; struct SBECoreUtil::CW32SID *
0x180060b7c  mov     rcx, rax; this
0x180060b7f  mov     [rsp+68h+var_40], 100000h; unsigned int
0x180060b87  call    ??0CSBESecurityObject@SBECoreUtil@@QEAA@PEAVCW32SID@1@W4_ACCESS_MODE@@K1KPEAK@Z; SBECoreUtil::CSBESecurityObject::CSBESecurityObject(SBECoreUtil::CW32SID *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,ulong *)
0x180060b8c  mov     rdi, rax
0x180060b8f  test    rax, rax
0x180060b92  jz      short loc_180060BB9
0x180060b94  mov     ebx, [rsp+68h+arg_10]
0x180060b9b  test    ebx, ebx
0x180060b9d  jz      short loc_180060BB3
0x180060b9f  jle     loc_180060C75
0x180060ba5  movzx   ebx, bx
0x180060ba8  or      ebx, 80070000h
0x180060bae  jmp     loc_180060C75
0x180060bb3  mov     rcx, [rax+38h]
0x180060bb7  jmp     short loc_180060BC5
0x180060bb9  mov     ebx, 8007000Eh
0x180060bbe  jmp     loc_180060C88
0x180060bc3  xor     ecx, ecx; lpMutexAttributes
0x180060bc5  mov     r8, rbp; lpName
0x180060bc8  mov     edx, r14d; bInitialOwner
0x180060bcb  call    cs:__imp_CreateMutexW
0x180060bd1  mov     [rsp+68h+var_28], rax
0x180060bd6  mov     rbp, rax
0x180060bd9  test    rax, rax
0x180060bdc  jz      short loc_180060C10
0x180060bde  call    cs:__imp_GetLastError
0x180060be4  mov     ebx, eax
0x180060be6  cmp     esi, 1
0x180060be9  jnz     short loc_180060BF9
0x180060beb  cmp     eax, 0B7h
0x180060bf0  jnz     short loc_180060C5B
0x180060bf2  mov     ebx, 800700B7h
0x180060bf7  jmp     short loc_180060C70
0x180060bf9  cmp     esi, 3
0x180060bfc  jnz     short loc_180060C5B
0x180060bfe  cmp     eax, 0B7h
0x180060c03  jz      short loc_180060C5B
0x180060c05  test    eax, eax
0x180060c07  jnz     short loc_180060C1A
0x180060c09  mov     ebx, 80004005h
0x180060c0e  jmp     short loc_180060C70
0x180060c10  call    cs:__imp_GetLastError
0x180060c16  mov     ebx, eax
0x180060c18  test    eax, eax
0x180060c1a  jle     short loc_180060C70
0x180060c1c  movzx   ebx, ax
0x180060c1f  or      ebx, 80070000h
0x180060c25  jmp     short loc_180060C70
0x180060c27  mov     r8, rbp; lpName
0x180060c2a  xor     edx, edx; bInheritHandle
0x180060c2c  mov     ecx, 100000h; dwDesiredAccess
0x180060c31  call    cs:__imp_OpenMutexW
0x180060c37  mov     [rsp+68h+var_28], rax
0x180060c3c  mov     rbp, rax
0x180060c3f  test    rax, rax
0x180060c42  jnz     short loc_180060C5B
0x180060c44  call    cs:__imp_GetLastError
0x180060c4a  mov     ebx, eax
0x180060c4c  test    eax, eax
0x180060c4e  jle     short loc_180060C88
0x180060c50  movzx   ebx, ax
0x180060c53  or      ebx, 80070000h
0x180060c59  jmp     short loc_180060C88
0x180060c5b  mov     r8, [rsp+68h+arg_20]; struct CMutexLock **
0x180060c63  mov     edx, r14d; int
0x180060c66  mov     rcx, rbp; void *
0x180060c69  call    ?CreateInstance@CMutexLock@SBECoreUtil@@SAJPEAXHPEAPEAV12@@Z; SBECoreUtil::CMutexLock::CreateInstance(void *,int,SBECoreUtil::CMutexLock * *)
0x180060c6e  mov     ebx, eax
0x180060c70  test    rdi, rdi
0x180060c73  jz      short loc_180060C88
0x180060c75  mov     r8, [rdi]
0x180060c78  mov     edx, 1
0x180060c7d  mov     rcx, rdi
0x180060c80  mov     rax, [r8]
0x180060c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c88  lea     rcx, [rsp+68h+var_28]; this
0x180060c8d  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x180060c92  mov     rbp, [rsp+68h+arg_8]
0x180060c97  mov     eax, ebx
0x180060c99  mov     rbx, [rsp+68h+arg_0]
0x180060c9e  add     rsp, 50h
0x180060ca2  pop     r14
0x180060ca4  pop     rdi
0x180060ca5  pop     rsi
0x180060ca6  retn
```
