# CThreadContext::EnablePrivileges(ulong *,ulong)

- ea: `0x180005b78`
- end: `0x180005cde`
- name: `?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z`
- size: `358`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this, unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004f48`
- `0x180013748`
- `0x180013984`
- `0x180013a54`
- `0x18001b3e8`

## callees

- `0x180005540`
- `0x180005a48`
- `0x180005b30`
- `0x180005b78`
- `0x180005cf0`
- `0x180005d48`
- `0x180006138`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180005c6d`
- `ntdll!RtlAdjustPrivilege` at `0x180005c6d`

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
              if ( !CThreadContext::PrivilegeEnabled(v12, a2[v13]) )
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
0x180005b78  mov     [rsp+arg_8], rbx
0x180005b7d  mov     [rsp+arg_18], rbp
0x180005b82  push    rsi
0x180005b83  push    rdi
0x180005b84  push    r12
0x180005b86  push    r14
0x180005b88  push    r15
0x180005b8a  sub     rsp, 20h
0x180005b8e  mov     esi, r8d
0x180005b91  lea     rdi, [rcx+20h]
0x180005b95  mov     eax, 4
0x180005b9a  mov     qword ptr [rdi], 0
0x180005ba1  mov     r12, rdx
0x180005ba4  mov     [rsp+48h+arg_0], 0
0x180005bad  mul     rsi
0x180005bb0  mov     rbp, rcx
0x180005bb3  mov     r14d, r8d
0x180005bb6  test    rdx, rdx
0x180005bb9  jnz     loc_180005CB7
0x180005bbf  mov     rdx, rdi; void **
0x180005bc2  mov     rcx, rax; dwBytes
0x180005bc5  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180005bca  mov     ebx, eax
0x180005bcc  test    eax, eax
0x180005bce  js      loc_180005C9D
0x180005bd4  mov     eax, 4
0x180005bd9  mov     [rsp+48h+arg_0], 0
0x180005be2  mul     r14
0x180005be5  lea     r15, [rbp+28h]
0x180005be9  mov     qword ptr [r15], 0
0x180005bf0  test    rdx, rdx
0x180005bf3  jnz     loc_180005CBE
0x180005bf9  mov     rdx, r15; void **
0x180005bfc  mov     rcx, rax; dwBytes
0x180005bff  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180005c04  mov     ebx, eax
0x180005c06  test    eax, eax
0x180005c08  js      loc_180005CC3
0x180005c0e  xor     r8d, r8d
0x180005c11  mov     [rbp+18h], esi
0x180005c14  test    esi, esi
0x180005c16  jz      short loc_180005C39
0x180005c18  xor     edx, edx
0x180005c1a  mov     eax, [r12+rdx*4]
0x180005c1e  inc     r8d
0x180005c21  mov     rcx, [rdi]
0x180005c24  mov     [rcx+rdx*4], eax
0x180005c27  mov     rax, [r15]
0x180005c2a  mov     dword ptr [rax+rdx*4], 0
0x180005c31  inc     rdx
0x180005c34  cmp     r8d, esi
0x180005c37  jb      short loc_180005C1A
0x180005c39  mov     rcx, rbp; this
0x180005c3c  call    ?ImpersonateSelf@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateSelf(void)
0x180005c41  mov     ebx, eax
0x180005c43  test    eax, eax
0x180005c45  js      short loc_180005C9D
0x180005c47  xor     edi, edi
0x180005c49  test    esi, esi
0x180005c4b  jz      short loc_180005C9D
0x180005c4d  mov     edx, [r12+rdi*4]; unsigned int
0x180005c51  call    ?PrivilegeEnabled@CThreadContext@@QEAAHK@Z; CThreadContext::PrivilegeEnabled(ulong)
0x180005c56  test    eax, eax
0x180005c58  jnz     short loc_180005C97
0x180005c5a  mov     ecx, [r12+rdi*4]; Privilege
0x180005c5e  lea     r9, [rsp+48h+OldValue]; OldValue
0x180005c63  mov     r8b, 1; ForThread
0x180005c66  mov     [rsp+48h+OldValue], al
0x180005c6a  mov     dl, r8b; NewValue
0x180005c6d  call    cs:__imp_RtlAdjustPrivilege
0x180005c74  nop     dword ptr [rax+rax+00h]
0x180005c79  mov     ecx, eax; int
0x180005c7b  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180005c80  mov     ebx, eax
0x180005c82  test    eax, eax
0x180005c84  js      short loc_180005CD4
0x180005c86  cmp     [rsp+48h+OldValue], 0
0x180005c8b  jnz     short loc_180005C97
0x180005c8d  mov     rax, [r15]
0x180005c90  mov     dword ptr [rax+rdi*4], 1
0x180005c97  inc     edi
0x180005c99  cmp     edi, esi
0x180005c9b  jb      short loc_180005C4D
0x180005c9d  mov     rbp, [rsp+48h+arg_18]
0x180005ca2  mov     eax, ebx
0x180005ca4  mov     rbx, [rsp+48h+arg_8]
0x180005ca9  add     rsp, 20h
0x180005cad  pop     r15
0x180005caf  pop     r14
0x180005cb1  pop     r12
0x180005cb3  pop     rdi
0x180005cb4  pop     rsi
0x180005cb5  retn
0x180005cb7  mov     ebx, 80070216h
0x180005cbc  jmp     short loc_180005C9D
0x180005cbe  mov     ebx, 80070216h
0x180005cc3  mov     rcx, [rdi]; lpMem
0x180005cc6  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005ccb  mov     qword ptr [rdi], 0
0x180005cd2  jmp     short loc_180005C9D
0x180005cd4  mov     rcx, rbp; this
0x180005cd7  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005cdc  jmp     short loc_180005C9D
```
