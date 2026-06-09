# CThreadContext::EnablePrivileges(ulong *,ulong)

- ea: `0x18000542c`
- end: `0x18000558b`
- name: `?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z`
- size: `351`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this, unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004938`
- `0x18001274c`
- `0x1800128cc`
- `0x180012998`
- `0x18001995c`

## callees

- `0x180004ea8`
- `0x180005320`
- `0x1800053f0`
- `0x18000542c`
- `0x1800055a0`
- `0x1800055ec`
- `0x180005980`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180005521`
- `ntdll!RtlAdjustPrivilege` at `0x180005521`

## pseudocode

```c
__int64 __fastcall CThreadContext::EnablePrivileges(CThreadContext *this, unsigned int *a2, unsigned int a3)
{
  void **v4; // rdi
  unsigned __int64 v7; // r14
  int v8; // ebx
  _QWORD *v9; // r15
  unsigned int v10; // r8d
  __int64 v11; // rdx
  CThreadContext *v12; // rcx
  __int64 v13; // rdi
  ULONG v14; // ecx
  NTSTATUS v15; // eax
  unsigned __int8 OldValue; // [rsp+60h] [rbp+18h] BYREF

  v4 = (void **)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  v7 = a3;
  if ( !is_mul_ok(a3, 4u) )
    return (unsigned int)-2147024362;
  v8 = ResultFromHeapAlloc(4LL * a3, (void **)this + 4);
  if ( v8 >= 0 )
  {
    v9 = (_QWORD *)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    if ( is_mul_ok(v7, 4u) )
    {
      v8 = ResultFromHeapAlloc(4 * v7, (void **)this + 5);
      if ( v8 >= 0 )
      {
        v10 = 0;
        *((_DWORD *)this + 6) = a3;
        if ( a3 )
        {
          v11 = 0;
          do
          {
            ++v10;
            *((_DWORD *)*v4 + v11) = a2[v11];
            *(_DWORD *)(*v9 + 4 * v11++) = 0;
          }
          while ( v10 < a3 );
        }
        v8 = CThreadContext::ImpersonateSelf(this);
        if ( v8 >= 0 )
        {
          v13 = 0;
          if ( a3 )
          {
            while ( 1 )
            {
              if ( !(unsigned int)CThreadContext::PrivilegeEnabled(v12, a2[v13]) )
              {
                v14 = a2[v13];
                OldValue = 0;
                v15 = RtlAdjustPrivilege(v14, 1u, 1u, &OldValue);
                v8 = ResultFromWin32FromStatus(v15);
                if ( v8 < 0 )
                {
                  CThreadContext::RevertPrivileges(this);
                  return (unsigned int)v8;
                }
                if ( !OldValue )
                  *(_DWORD *)(*v9 + 4 * v13) = 1;
              }
              v13 = (unsigned int)(v13 + 1);
              if ( (unsigned int)v13 >= a3 )
                return (unsigned int)v8;
            }
          }
        }
        return (unsigned int)v8;
      }
    }
    else
    {
      v8 = -2147024362;
    }
    ResultFromHeapFree(*v4);
    *v4 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000542c  mov     [rsp+arg_8], rbx
0x180005431  mov     [rsp+arg_18], rbp
0x180005436  push    rsi
0x180005437  push    rdi
0x180005438  push    r12
0x18000543a  push    r14
0x18000543c  push    r15
0x18000543e  sub     rsp, 20h
0x180005442  mov     esi, r8d
0x180005445  lea     rdi, [rcx+20h]
0x180005449  mov     eax, 4
0x18000544e  mov     qword ptr [rdi], 0
0x180005455  mov     r12, rdx
0x180005458  mov     [rsp+48h+arg_0], 0
0x180005461  mul     rsi
0x180005464  mov     rbp, rcx
0x180005467  mov     r14d, r8d
0x18000546a  test    rdx, rdx
0x18000546d  jnz     loc_180005564
0x180005473  mov     rdx, rdi; void **
0x180005476  mov     rcx, rax; dwBytes
0x180005479  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000547e  mov     ebx, eax
0x180005480  test    eax, eax
0x180005482  js      loc_18000554B
0x180005488  mov     eax, 4
0x18000548d  mov     [rsp+48h+arg_0], 0
0x180005496  mul     r14
0x180005499  lea     r15, [rbp+28h]
0x18000549d  mov     qword ptr [r15], 0
0x1800054a4  test    rdx, rdx
0x1800054a7  jnz     loc_18000556B
0x1800054ad  mov     rdx, r15; void **
0x1800054b0  mov     rcx, rax; dwBytes
0x1800054b3  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800054b8  mov     ebx, eax
0x1800054ba  test    eax, eax
0x1800054bc  js      loc_180005570
0x1800054c2  xor     r8d, r8d
0x1800054c5  mov     [rbp+18h], esi
0x1800054c8  test    esi, esi
0x1800054ca  jz      short loc_1800054ED
0x1800054cc  xor     edx, edx
0x1800054ce  mov     eax, [r12+rdx*4]
0x1800054d2  inc     r8d
0x1800054d5  mov     rcx, [rdi]
0x1800054d8  mov     [rcx+rdx*4], eax
0x1800054db  mov     rax, [r15]
0x1800054de  mov     dword ptr [rax+rdx*4], 0
0x1800054e5  inc     rdx
0x1800054e8  cmp     r8d, esi
0x1800054eb  jb      short loc_1800054CE
0x1800054ed  mov     rcx, rbp; this
0x1800054f0  call    ?ImpersonateSelf@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateSelf(void)
0x1800054f5  mov     ebx, eax
0x1800054f7  test    eax, eax
0x1800054f9  js      short loc_18000554B
0x1800054fb  xor     edi, edi
0x1800054fd  test    esi, esi
0x1800054ff  jz      short loc_18000554B
0x180005501  mov     edx, [r12+rdi*4]; unsigned int
0x180005505  call    ?PrivilegeEnabled@CThreadContext@@QEAAHK@Z; CThreadContext::PrivilegeEnabled(ulong)
0x18000550a  test    eax, eax
0x18000550c  jnz     short loc_180005545
0x18000550e  mov     ecx, [r12+rdi*4]; Privilege
0x180005512  lea     r9, [rsp+48h+OldValue]; OldValue
0x180005517  mov     r8b, 1; ForThread
0x18000551a  mov     [rsp+48h+OldValue], al
0x18000551e  mov     dl, r8b; NewValue
0x180005521  call    cs:__imp_RtlAdjustPrivilege
0x180005527  mov     ecx, eax; int
0x180005529  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000552e  mov     ebx, eax
0x180005530  test    eax, eax
0x180005532  js      short loc_180005581
0x180005534  cmp     [rsp+48h+OldValue], 0
0x180005539  jnz     short loc_180005545
0x18000553b  mov     rax, [r15]
0x18000553e  mov     dword ptr [rax+rdi*4], 1
0x180005545  inc     edi
0x180005547  cmp     edi, esi
0x180005549  jb      short loc_180005501
0x18000554b  mov     rbp, [rsp+48h+arg_18]
0x180005550  mov     eax, ebx
0x180005552  mov     rbx, [rsp+48h+arg_8]
0x180005557  add     rsp, 20h
0x18000555b  pop     r15
0x18000555d  pop     r14
0x18000555f  pop     r12
0x180005561  pop     rdi
0x180005562  pop     rsi
0x180005563  retn
0x180005564  mov     ebx, 80070216h
0x180005569  jmp     short loc_18000554B
0x18000556b  mov     ebx, 80070216h
0x180005570  mov     rcx, [rdi]; lpMem
0x180005573  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005578  mov     qword ptr [rdi], 0
0x18000557f  jmp     short loc_18000554B
0x180005581  mov     rcx, rbp; this
0x180005584  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005589  jmp     short loc_18000554B
```
