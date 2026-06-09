# IIS_VDIR::Initialize(ushort const *,INativeConfigurationElement *)

- ea: `0x18001c854`
- end: `0x18001c9ff`
- name: `?Initialize@IIS_VDIR@@QEAAJPEBGPEAVINativeConfigurationElement@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(IIS_VDIR *__hidden this, const unsigned __int16 *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001cdd0`

## callees

- `0x180019d58`
- `0x18001c854`
- `0x18001d154`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001c9d6`
- `msvcrt!_wcsnicmp` at `0x18001c9d6`
- `msvcrt!wcsrchr` at `0x18001c913`
- `msvcrt!wcsrchr` at `0x18001c913`
- `iisutil!MakePathCanonicalizationProof` at `0x18001c9a5`
- `iisutil!MakePathCanonicalizationProof` at `0x18001c9a5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c89a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c92a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c89a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c92a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c8fc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c8fc`

## string_xrefs

- `0x18001c980`: `physicalPath`

## pseudocode

```c
__int64 __fastcall IIS_VDIR::Initialize(
        const wchar_t **this,
        const unsigned __int16 *a2,
        struct INativeConfigurationElement *a3)
{
  int IsSlashTerminated; // ebx
  STRU *v7; // rbp
  const unsigned __int16 *v8; // rdx
  wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rax
  const unsigned __int16 *v13; // [rsp+68h] [rbp+10h] BYREF
  const unsigned __int16 *v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  if ( *a2 != 47 )
    return (unsigned int)-2147024809;
  v7 = (STRU *)(this + 6);
  IsSlashTerminated = STRU::Copy((STRU *)(this + 6), a2);
  if ( IsSlashTerminated >= 0 )
  {
    IsSlashTerminated = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a3 + 64LL))(
                          a3,
                          L"path",
                          &v13,
                          0,
                          0);
    if ( IsSlashTerminated >= 0 )
    {
      v8 = v13;
      if ( *v13 != 47 )
        return (unsigned int)-2147024809;
      if ( !a2[1] || !v13[1] )
        v8 = ++v13;
      IsSlashTerminated = STRU::Append(v7, v8);
      if ( IsSlashTerminated >= 0 )
      {
        v9 = wcsrchr(this[10], 0x2Fu);
        if ( v9 )
        {
          IsSlashTerminated = STRU::Copy((STRU *)(this + 13), v9 + 1);
          if ( IsSlashTerminated >= 0 )
          {
            IsSlashTerminated = EnsureUriPathIsSlashTerminated(v7);
            if ( IsSlashTerminated >= 0 )
            {
              v10 = this[10];
              v11 = this[17];
              *this = v10;
              this[3] = v11;
              if ( !v10[1] )
                *((_DWORD *)this + 89) = 1;
              IsSlashTerminated = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a3 + 64LL))(
                                    a3,
                                    L"physicalPath",
                                    &v14,
                                    0,
                                    0);
              if ( IsSlashTerminated >= 0 )
              {
                IsSlashTerminated = MakePathCanonicalizationProof(v14, (struct STRU *)(this + 20));
                if ( IsSlashTerminated >= 0 )
                {
                  IsSlashTerminated = IIS_VDIR::ReadCredentials((IIS_VDIR *)this, a3);
                  if ( IsSlashTerminated >= 0 && !_wcsnicmp(this[24], L"\\\\?\\UNC\\", 8u) )
                    *((_DWORD *)this + 90) = 1;
                }
              }
            }
          }
          return (unsigned int)IsSlashTerminated;
        }
        return (unsigned int)-2147024809;
      }
    }
  }
  return (unsigned int)IsSlashTerminated;
}

```

## disassembly

```asm
0x18001c854  mov     rax, rsp
0x18001c857  mov     [rax+8], rbx
0x18001c85b  mov     [rax+18h], rbp
0x18001c85f  push    rsi
0x18001c860  push    rdi
0x18001c861  push    r12
0x18001c863  push    r14
0x18001c865  push    r15
0x18001c867  sub     rsp, 30h
0x18001c86b  xor     r15d, r15d
0x18001c86e  mov     r14, r8
0x18001c871  mov     rsi, rdx
0x18001c874  mov     [rax+10h], r15
0x18001c878  mov     rdi, rcx
0x18001c87b  mov     [rax+20h], r15
0x18001c87f  lea     r12d, [r15+2Fh]
0x18001c883  cmp     [rdx], r12w
0x18001c887  jz      short loc_18001C893
0x18001c889  mov     ebx, 80070057h
0x18001c88e  jmp     loc_18001C9E6
0x18001c893  lea     rbp, [rcx+30h]
0x18001c897  mov     rcx, rbp
0x18001c89a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c8a0  mov     ebx, eax
0x18001c8a2  test    eax, eax
0x18001c8a4  js      loc_18001C9E6
0x18001c8aa  mov     rax, [r14]
0x18001c8ad  lea     r8, [rsp+58h+arg_8]
0x18001c8b2  xor     r9d, r9d
0x18001c8b5  mov     [rsp+58h+var_38], r15
0x18001c8ba  lea     rdx, aPath; "path"
0x18001c8c1  mov     rcx, r14
0x18001c8c4  mov     rax, [rax+40h]
0x18001c8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8cd  mov     ebx, eax
0x18001c8cf  test    eax, eax
0x18001c8d1  js      loc_18001C9E6
0x18001c8d7  mov     rdx, [rsp+58h+arg_8]
0x18001c8dc  cmp     [rdx], r12w
0x18001c8e0  jnz     short loc_18001C889
0x18001c8e2  cmp     [rsi+2], r15w
0x18001c8e7  jz      short loc_18001C8F0
0x18001c8e9  cmp     [rdx+2], r15w
0x18001c8ee  jnz     short loc_18001C8F9
0x18001c8f0  add     rdx, 2
0x18001c8f4  mov     [rsp+58h+arg_8], rdx
0x18001c8f9  mov     rcx, rbp
0x18001c8fc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001c902  mov     ebx, eax
0x18001c904  test    eax, eax
0x18001c906  js      loc_18001C9E6
0x18001c90c  mov     rcx, [rdi+50h]; Str
0x18001c910  mov     edx, r12d; Ch
0x18001c913  call    cs:__imp_wcsrchr
0x18001c919  test    rax, rax
0x18001c91c  jz      loc_18001C889
0x18001c922  lea     rdx, [rax+2]
0x18001c926  lea     rcx, [rdi+68h]
0x18001c92a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c930  mov     ebx, eax
0x18001c932  test    eax, eax
0x18001c934  js      loc_18001C9E6
0x18001c93a  mov     rcx, rbp; struct STRU *
0x18001c93d  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x18001c942  mov     ebx, eax
0x18001c944  test    eax, eax
0x18001c946  js      loc_18001C9E6
0x18001c94c  mov     rcx, [rdi+50h]
0x18001c950  mov     esi, 1
0x18001c955  mov     rax, [rdi+88h]
0x18001c95c  mov     [rdi], rcx
0x18001c95f  mov     [rdi+18h], rax
0x18001c963  cmp     [rcx+2], r15w
0x18001c968  jnz     short loc_18001C970
0x18001c96a  mov     [rdi+164h], esi
0x18001c970  mov     rax, [r14]
0x18001c973  lea     r8, [rsp+58h+arg_18]
0x18001c978  xor     r9d, r9d
0x18001c97b  mov     [rsp+58h+var_38], r15
0x18001c980  lea     rdx, aPhysicalpath; "physicalPath"
0x18001c987  mov     rcx, r14
0x18001c98a  mov     rax, [rax+40h]
0x18001c98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c993  mov     ebx, eax
0x18001c995  test    eax, eax
0x18001c997  js      short loc_18001C9E6
0x18001c999  mov     rcx, [rsp+58h+arg_18]
0x18001c99e  lea     rdx, [rdi+0A0h]
0x18001c9a5  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18001c9ab  mov     ebx, eax
0x18001c9ad  test    eax, eax
0x18001c9af  js      short loc_18001C9E6
0x18001c9b1  mov     rdx, r14; struct INativeConfigurationElement *
0x18001c9b4  mov     rcx, rdi; this
0x18001c9b7  call    ?ReadCredentials@IIS_VDIR@@AEAAJPEAVINativeConfigurationElement@@@Z; IIS_VDIR::ReadCredentials(INativeConfigurationElement *)
0x18001c9bc  mov     ebx, eax
0x18001c9be  test    eax, eax
0x18001c9c0  js      short loc_18001C9E6
0x18001c9c2  mov     rcx, [rdi+0C0h]; String1
0x18001c9c9  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x18001c9d0  mov     r8d, 8; MaxCount
0x18001c9d6  call    cs:__imp__wcsnicmp
0x18001c9dc  test    eax, eax
0x18001c9de  jnz     short loc_18001C9E6
0x18001c9e0  mov     [rdi+168h], esi
0x18001c9e6  mov     rbp, [rsp+58h+arg_10]
0x18001c9eb  mov     eax, ebx
0x18001c9ed  mov     rbx, [rsp+58h+arg_0]
0x18001c9f2  add     rsp, 30h
0x18001c9f6  pop     r15
0x18001c9f8  pop     r14
0x18001c9fa  pop     r12
0x18001c9fc  pop     rdi
0x18001c9fd  pop     rsi
0x18001c9fe  retn
```
