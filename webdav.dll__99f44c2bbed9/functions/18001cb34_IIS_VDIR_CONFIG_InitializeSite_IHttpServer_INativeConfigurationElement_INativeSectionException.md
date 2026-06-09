# IIS_VDIR_CONFIG::InitializeSite(IHttpServer *,INativeConfigurationElement *,INativeSectionException * *)

- ea: `0x18001cb34`
- end: `0x18001ccb9`
- name: `?InitializeSite@IIS_VDIR_CONFIG@@QEAAJPEAVIHttpServer@@PEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(IIS_VDIR_CONFIG *__hidden this, struct IHttpServer *, struct INativeConfigurationElement *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010384`

## callees

- `0x180004474`
- `0x18001ca08`
- `0x18001cb34`
- `0x180023010`

## import_xrefs

- `msvcrt!qsort` at `0x18001cca4`
- `msvcrt!qsort` at `0x18001cca4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001cc2a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001cc2a`

## pseudocode

```c
__int64 __fastcall IIS_VDIR_CONFIG::InitializeSite(
        IIS_VDIR_CONFIG *this,
        struct IHttpServer *a2,
        struct INativeConfigurationElement *a3,
        struct INativeSectionException **a4)
{
  __int64 v4; // rax
  struct IHttpServer *v5; // r14
  __int64 (__fastcall *v7)(struct INativeConfigurationElement *, struct IHttpServer **); // rax
  int v8; // ebx
  unsigned int i; // esi
  struct STATIC_WSTRING_HASH_RECORD **v10; // r11
  __int64 v11; // rcx
  struct STATIC_WSTRING_HASH_RECORD **v12; // rbx
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  __int64 v14; // r11
  unsigned int v15; // eax
  struct STATIC_WSTRING_HASH_RECORD *v17; // [rsp+20h] [rbp-10h] BYREF
  int v18; // [rsp+28h] [rbp-8h]
  int v19; // [rsp+2Ch] [rbp-4h]
  struct IHttpServer *v20; // [rsp+68h] [rbp+38h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+70h] [rbp+40h] BYREF
  struct INativeSectionException **v22; // [rsp+78h] [rbp+48h] BYREF

  v22 = a4;
  v20 = a2;
  v4 = *(_QWORD *)a3;
  v5 = g_pGlobalInfo;
  v20 = 0;
  v21 = 0;
  v7 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct IHttpServer **))(v4 + 40);
  LODWORD(v22) = 0;
  v8 = v7(a3, &v20);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IHttpServer *, struct INativeSectionException ***))(*(_QWORD *)v20 + 24LL))(
           v20,
           &v22);
    if ( v8 >= 0 )
    {
      for ( i = 0; i < (unsigned int)v22; ++i )
      {
        v8 = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v20 + 32LL))(
               v20,
               i,
               &v21);
        if ( v8 < 0 )
          break;
        v8 = IIS_VDIR_CONFIG::InitializeApplication(this, v5, v21);
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
        if ( v8 < 0 )
          break;
      }
    }
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
    if ( v8 >= 0 )
    {
      if ( BUFFER::Resize((IIS_VDIR_CONFIG *)((char *)this + 2112), 8 * *((_DWORD *)this + 540)) )
      {
        v10 = (struct STATIC_WSTRING_HASH_RECORD **)*((_QWORD *)this + 268);
        v11 = 0;
        v12 = v10;
        v19 = 0;
        do
        {
          Next = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)this + v11);
          if ( Next )
            break;
          v11 = (unsigned int)(v11 + 1);
        }
        while ( (unsigned int)v11 < 0x83 );
        v18 = v11;
        v17 = Next;
        if ( Next )
        {
          while ( 1 )
          {
            *v10 = Next;
            Next = STATIC_WSTRING_HASH::FindNext(this, (struct STATIC_WSTRING_HASH_ITER *)&v17);
            if ( !Next )
              break;
            v10 = (struct STATIC_WSTRING_HASH_RECORD **)(v14 + 8);
          }
        }
        v15 = *((_DWORD *)this + 540);
        if ( v15 > 1 )
          qsort(v12, v15, 8u, SortVDirLengthCallback);
        return 0;
      }
      else
      {
        return (unsigned int)-2147024888;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cb34  mov     [rsp-28h+arg_18], r9
0x18001cb39  mov     [rsp-28h+arg_8], rdx
0x18001cb3e  push    rbp
0x18001cb3f  push    rbx
0x18001cb40  push    rsi
0x18001cb41  push    rdi
0x18001cb42  push    r14
0x18001cb44  mov     rbp, rsp
0x18001cb47  sub     rsp, 30h
0x18001cb4b  mov     rax, [r8]
0x18001cb4e  lea     rdx, [rbp+arg_8]
0x18001cb52  mov     r14, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18001cb59  mov     rdi, rcx
0x18001cb5c  mov     rcx, r8
0x18001cb5f  mov     [rbp+arg_8], 0
0x18001cb67  mov     [rbp+arg_10], 0
0x18001cb6f  mov     rax, [rax+28h]
0x18001cb73  mov     dword ptr [rbp+arg_18], 0
0x18001cb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7f  mov     ebx, eax
0x18001cb81  test    eax, eax
0x18001cb83  js      loc_18001CCAC
0x18001cb89  mov     rcx, [rbp+arg_8]
0x18001cb8d  lea     rdx, [rbp+arg_18]
0x18001cb91  mov     rax, [rcx]
0x18001cb94  mov     rax, [rax+18h]
0x18001cb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb9d  mov     ebx, eax
0x18001cb9f  test    eax, eax
0x18001cba1  js      short loc_18001CBFA
0x18001cba3  xor     esi, esi
0x18001cba5  cmp     dword ptr [rbp+arg_18], esi
0x18001cba8  jbe     short loc_18001CBFA
0x18001cbaa  mov     rcx, [rbp+arg_8]
0x18001cbae  lea     r8, [rbp+arg_10]
0x18001cbb2  mov     edx, esi
0x18001cbb4  mov     rax, [rcx]
0x18001cbb7  mov     rax, [rax+20h]
0x18001cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc0  mov     ebx, eax
0x18001cbc2  test    eax, eax
0x18001cbc4  js      short loc_18001CBFA
0x18001cbc6  mov     r8, [rbp+arg_10]; struct INativeConfigurationElement *
0x18001cbca  mov     rdx, r14; struct IHttpServer *
0x18001cbcd  mov     rcx, rdi; this
0x18001cbd0  call    ?InitializeApplication@IIS_VDIR_CONFIG@@AEAAJPEAVIHttpServer@@PEAVINativeConfigurationElement@@@Z; IIS_VDIR_CONFIG::InitializeApplication(IHttpServer *,INativeConfigurationElement *)
0x18001cbd5  mov     rcx, [rbp+arg_10]
0x18001cbd9  mov     ebx, eax
0x18001cbdb  mov     rax, [rcx]
0x18001cbde  mov     rax, [rax+10h]
0x18001cbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbe7  mov     [rbp+arg_10], 0
0x18001cbef  test    ebx, ebx
0x18001cbf1  js      short loc_18001CBFA
0x18001cbf3  inc     esi
0x18001cbf5  cmp     esi, dword ptr [rbp+arg_18]
0x18001cbf8  jb      short loc_18001CBAA
0x18001cbfa  mov     rcx, [rbp+arg_8]
0x18001cbfe  mov     rax, [rcx]
0x18001cc01  mov     rax, [rax+10h]
0x18001cc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc0a  mov     [rbp+arg_8], 0
0x18001cc12  test    ebx, ebx
0x18001cc14  js      loc_18001CCAC
0x18001cc1a  mov     edx, [rdi+870h]
0x18001cc20  lea     rcx, [rdi+840h]
0x18001cc27  shl     edx, 3
0x18001cc2a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001cc30  test    al, al
0x18001cc32  jnz     short loc_18001CC3B
0x18001cc34  mov     ebx, 80070008h
0x18001cc39  jmp     short loc_18001CCAC
0x18001cc3b  mov     r11, [rdi+860h]
0x18001cc42  xor     ecx, ecx
0x18001cc44  mov     rbx, r11
0x18001cc47  mov     [rbp+var_4], 0
0x18001cc4e  mov     rax, [rdi+rcx*8]
0x18001cc52  test    rax, rax
0x18001cc55  jnz     short loc_18001CC61
0x18001cc57  inc     ecx
0x18001cc59  cmp     ecx, 83h
0x18001cc5f  jb      short loc_18001CC4E
0x18001cc61  mov     [rbp+var_8], ecx
0x18001cc64  mov     [rbp+var_10], rax
0x18001cc68  test    rax, rax
0x18001cc6b  jz      short loc_18001CC87
0x18001cc6d  lea     rdx, [rbp+var_10]; struct STATIC_WSTRING_HASH_ITER *
0x18001cc71  mov     [r11], rax
0x18001cc74  mov     rcx, rdi; this
0x18001cc77  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001cc7c  test    rax, rax
0x18001cc7f  jz      short loc_18001CC87
0x18001cc81  add     r11, 8
0x18001cc85  jmp     short loc_18001CC6D
0x18001cc87  mov     eax, [rdi+870h]
0x18001cc8d  cmp     eax, 1
0x18001cc90  jbe     short loc_18001CCAA
0x18001cc92  mov     edx, eax; NumOfElements
0x18001cc94  lea     r9, ?SortVDirLengthCallback@@YAHPEBX0@Z; CompareFunction
0x18001cc9b  mov     r8d, 8; SizeOfElements
0x18001cca1  mov     rcx, rbx; Base
0x18001cca4  call    cs:__imp_qsort
0x18001ccaa  xor     ebx, ebx
0x18001ccac  mov     eax, ebx
0x18001ccae  add     rsp, 30h
0x18001ccb2  pop     r14
0x18001ccb4  pop     rdi
0x18001ccb5  pop     rsi
0x18001ccb6  pop     rbx
0x18001ccb7  pop     rbp
0x18001ccb8  retn
```
