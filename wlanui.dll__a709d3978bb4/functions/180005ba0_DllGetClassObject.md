# DllGetClassObject

- ea: `0x180005ba0`
- end: `0x180005c98`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003728`
- `0x180005ba0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005c23`
- `KERNEL32!EnterCriticalSection` at `0x180005c23`
- `KERNEL32!LeaveCriticalSection` at `0x180005c4e`
- `KERNEL32!LeaveCriticalSection` at `0x180005c4e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT v6; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = qword_18002E9B8;
  if ( qword_18002E9B8 )
  {
    while ( *(_QWORD *)v7 )
    {
      if ( *(_QWORD *)(v7 + 16) )
      {
        rclsid = *(const IID *const *)v7;
        if ( v5->Data1 == **(_DWORD **)v7
          && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
          && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
          && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
        {
          v8 = (const IID *const *)(v7 + 32);
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          rclsid = *v8;
          if ( *v8 )
            v6 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                   rclsid,
                   riid,
                   ppv);
          break;
        }
      }
      v7 += 72;
    }
  }
  if ( !*ppv && !v6 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v6;
}

```

## disassembly

```asm
0x180005ba0  push    rbx
0x180005ba2  push    rbp
0x180005ba3  push    rsi
0x180005ba4  push    rdi
0x180005ba5  push    r14
0x180005ba7  push    r15
0x180005ba9  sub     rsp, 28h
0x180005bad  mov     rsi, r8
0x180005bb0  mov     r15, rdx
0x180005bb3  mov     rbp, rcx
0x180005bb6  test    r8, r8
0x180005bb9  jnz     short loc_180005BC5
0x180005bbb  mov     edi, 80004003h
0x180005bc0  jmp     loc_180005C89
0x180005bc5  mov     qword ptr [r8], 0
0x180005bcc  xor     edi, edi
0x180005bce  mov     rbx, cs:qword_18002E9B8
0x180005bd5  test    rbx, rbx
0x180005bd8  jz      loc_180005C6F
0x180005bde  jmp     short loc_180005C0C
0x180005be0  cmp     [rbx+10h], rdi
0x180005be4  jz      short loc_180005C08
0x180005be6  mov     rcx, [rbx]
0x180005be9  mov     eax, [rcx]
0x180005beb  cmp     [rbp+0], eax
0x180005bee  jnz     short loc_180005C08
0x180005bf0  mov     eax, [rcx+4]
0x180005bf3  cmp     [rbp+4], eax
0x180005bf6  jnz     short loc_180005C08
0x180005bf8  mov     eax, [rcx+8]
0x180005bfb  cmp     [rbp+8], eax
0x180005bfe  jnz     short loc_180005C08
0x180005c00  mov     eax, [rcx+0Ch]
0x180005c03  cmp     [rbp+0Ch], eax
0x180005c06  jz      short loc_180005C13
0x180005c08  add     rbx, 48h ; 'H'
0x180005c0c  cmp     [rbx], rdi
0x180005c0f  jnz     short loc_180005BE0
0x180005c11  jmp     short loc_180005C6F
0x180005c13  lea     r14, [rbx+20h]
0x180005c17  cmp     [r14], rdi
0x180005c1a  jnz     short loc_180005C54
0x180005c1c  lea     rcx, CriticalSection; lpCriticalSection
0x180005c23  call    cs:__imp_EnterCriticalSection
0x180005c29  cmp     [r14], rdi
0x180005c2c  jnz     short loc_180005C47
0x180005c2e  mov     rcx, [rbx+18h]
0x180005c32  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005c39  mov     rax, [rbx+10h]
0x180005c3d  mov     r8, r14
0x180005c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c45  mov     edi, eax
0x180005c47  lea     rcx, CriticalSection; lpCriticalSection
0x180005c4e  call    cs:__imp_LeaveCriticalSection
0x180005c54  mov     rcx, [r14]
0x180005c57  test    rcx, rcx
0x180005c5a  jz      short loc_180005C6F
0x180005c5c  mov     rax, [rcx]
0x180005c5f  mov     r8, rsi
0x180005c62  mov     rdx, r15
0x180005c65  mov     rax, [rax]
0x180005c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c6d  mov     edi, eax
0x180005c6f  cmp     qword ptr [rsi], 0
0x180005c73  jnz     short loc_180005C89
0x180005c75  test    edi, edi
0x180005c77  jnz     short loc_180005C89
0x180005c79  mov     r9, rsi; void **
0x180005c7c  mov     r8, r15; struct _GUID *
0x180005c7f  mov     rdx, rbp; struct _GUID *
0x180005c82  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180005c87  mov     edi, eax
0x180005c89  mov     eax, edi
0x180005c8b  add     rsp, 28h
0x180005c8f  pop     r15
0x180005c91  pop     r14
0x180005c93  pop     rdi
0x180005c94  pop     rsi
0x180005c95  pop     rbp
0x180005c96  pop     rbx
0x180005c97  retn
```
