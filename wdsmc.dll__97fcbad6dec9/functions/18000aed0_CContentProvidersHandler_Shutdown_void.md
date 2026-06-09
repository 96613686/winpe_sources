# CContentProvidersHandler::Shutdown(void)

- ea: `0x18000aed0`
- end: `0x18000b00c`
- name: `?Shutdown@CContentProvidersHandler@@QEAAKXZ`
- size: `316`
- prototype: `unsigned int __fastcall(CContentProvidersHandler *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180005a4c`
- `0x180009130`
- `0x18000aa44`

## callees

- `0x180009ab8`
- `0x18000aed0`
- `0x18001a9a8`
- `0x180026d70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000afc2`
- `KERNEL32!DeleteCriticalSection` at `0x18000afc2`
- `ADVAPI32!RegCloseKey` at `0x18000afb4`
- `ADVAPI32!RegCloseKey` at `0x18000afb4`

## pseudocode

```c
__int64 __fastcall CContentProvidersHandler::Shutdown(struct _RTL_CRITICAL_SECTION **this)
{
  void (*v1)(unsigned int, const unsigned __int16 *, ...); // rax
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rax
  struct _RTL_CRITICAL_SECTION *SpinCount; // rax
  HANDLE *p_LockSemaphore; // rcx
  HKEY LockSemaphore; // rcx

  v1 = g_ErrLibTraceFunctionEx;
  if ( g_ErrLibTraceFunctionEx )
  {
    g_ErrLibTraceFunctionEx(0x10000u, L"-> CContentProvidersHandler::Shutdown");
    v1 = g_ErrLibTraceFunctionEx;
  }
  v3 = *this;
  if ( *this )
  {
    while ( 1 )
    {
      v4 = v3;
      if ( v3 )
        break;
LABEL_14:
      CContentProvider::Shutdown(v4);
      if ( v4 )
      {
        CContentProvider::Shutdown(v4);
        LockSemaphore = (HKEY)v4[1].LockSemaphore;
        if ( LockSemaphore )
        {
          RegCloseKey(LockSemaphore);
          v4[1].LockSemaphore = 0;
        }
        DeleteCriticalSection(v4);
        operator delete(v4);
      }
      if ( !v3 )
      {
        v1 = g_ErrLibTraceFunctionEx;
        goto LABEL_20;
      }
    }
    v5 = *this;
    v6 = this[1];
    if ( *this == v6 )
    {
      this[1] = 0;
      *this = 0;
    }
    else
    {
      if ( v3 == v5 )
      {
        v7 = (struct _RTL_CRITICAL_SECTION *)v5[4].LockSemaphore;
        *this = v7;
        v7[4].SpinCount = 0;
        v3 = *this;
LABEL_13:
        --*((_DWORD *)this + 5);
        goto LABEL_14;
      }
      if ( v3 != v6 )
      {
        p_LockSemaphore = &v3[4].LockSemaphore;
        v3 = (struct _RTL_CRITICAL_SECTION *)v3[4].LockSemaphore;
        *(_QWORD *)(v4[4].SpinCount + 184) = v3;
        *((_QWORD *)*p_LockSemaphore + 24) = v4[4].SpinCount;
        goto LABEL_13;
      }
      SpinCount = (struct _RTL_CRITICAL_SECTION *)v6[4].SpinCount;
      this[1] = SpinCount;
      SpinCount[4].LockSemaphore = 0;
    }
    v3 = 0;
    goto LABEL_13;
  }
LABEL_20:
  if ( v1 )
    v1(0x10000u, L"<- CContentProvidersHandler::Shutdown=%x", 0);
  return 0;
}

```

## disassembly

```asm
0x18000aed0  mov     [rsp+arg_0], rbx
0x18000aed5  mov     [rsp+arg_8], rsi
0x18000aeda  push    rdi
0x18000aedb  sub     rsp, 20h
0x18000aedf  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000aee6  mov     rdi, rcx
0x18000aee9  test    rax, rax
0x18000aeec  jz      short loc_18000AF07
0x18000aeee  lea     rdx, aCcontentprovid_0; "-> CContentProvidersHandler::Shutdown"
0x18000aef5  mov     ecx, 10000h
0x18000aefa  call    cs:__guard_dispatch_icall_fptr
0x18000af00  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000af07  mov     rbx, [rdi]
0x18000af0a  test    rbx, rbx
0x18000af0d  jz      loc_18000AFE0
0x18000af13  mov     rsi, rbx
0x18000af16  test    rbx, rbx
0x18000af19  jz      short loc_18000AF96
0x18000af1b  mov     rax, [rdi]
0x18000af1e  mov     rcx, [rdi+8]
0x18000af22  cmp     rax, rcx
0x18000af25  jnz     short loc_18000AF32
0x18000af27  and     qword ptr [rdi+8], 0
0x18000af2c  and     qword ptr [rdi], 0
0x18000af30  jmp     short loc_18000AF66
0x18000af32  cmp     rbx, rax
0x18000af35  jnz     short loc_18000AF4E
0x18000af37  mov     rax, [rax+0B8h]
0x18000af3e  mov     [rdi], rax
0x18000af41  and     qword ptr [rax+0C0h], 0
0x18000af49  mov     rbx, [rdi]
0x18000af4c  jmp     short loc_18000AF93
0x18000af4e  cmp     rbx, rcx
0x18000af51  jnz     short loc_18000AF6A
0x18000af53  mov     rax, [rcx+0C0h]
0x18000af5a  mov     [rdi+8], rax
0x18000af5e  and     qword ptr [rax+0B8h], 0
0x18000af66  xor     ebx, ebx
0x18000af68  jmp     short loc_18000AF93
0x18000af6a  mov     rax, [rsi+0C0h]
0x18000af71  lea     rcx, [rbx+0B8h]
0x18000af78  mov     rbx, [rcx]
0x18000af7b  mov     [rax+0B8h], rbx
0x18000af82  mov     rcx, [rcx]
0x18000af85  mov     rax, [rsi+0C0h]
0x18000af8c  mov     [rcx+0C0h], rax
0x18000af93  dec     dword ptr [rdi+14h]
0x18000af96  mov     rcx, rsi; lpCriticalSection
0x18000af99  call    ?Shutdown@CContentProvider@@QEAAKXZ; CContentProvider::Shutdown(void)
0x18000af9e  test    rsi, rsi
0x18000afa1  jz      short loc_18000AFD0
0x18000afa3  mov     rcx, rsi; lpCriticalSection
0x18000afa6  call    ?Shutdown@CContentProvider@@QEAAKXZ; CContentProvider::Shutdown(void)
0x18000afab  mov     rcx, [rsi+40h]; hKey
0x18000afaf  test    rcx, rcx
0x18000afb2  jz      short loc_18000AFBF
0x18000afb4  call    cs:__imp_RegCloseKey
0x18000afba  and     qword ptr [rsi+40h], 0
0x18000afbf  mov     rcx, rsi; lpCriticalSection
0x18000afc2  call    cs:__imp_DeleteCriticalSection
0x18000afc8  mov     rcx, rsi; void *
0x18000afcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000afd0  test    rbx, rbx
0x18000afd3  jnz     loc_18000AF13
0x18000afd9  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000afe0  test    rax, rax
0x18000afe3  jz      short loc_18000AFFA
0x18000afe5  xor     r8d, r8d
0x18000afe8  lea     rdx, aCcontentprovid_1; "<- CContentProvidersHandler::Shutdown=%"...
0x18000afef  mov     ecx, 10000h
0x18000aff4  call    cs:__guard_dispatch_icall_fptr
0x18000affa  mov     rbx, [rsp+28h+arg_0]
0x18000afff  xor     eax, eax
0x18000b001  mov     rsi, [rsp+28h+arg_8]
0x18000b006  add     rsp, 20h
0x18000b00a  pop     rdi
0x18000b00b  retn
```
