# CSsl3TlsContext::SetTokenBindingEKM(void)

- ea: `0x18001cc80`
- end: `0x18001cd43`
- name: `?SetTokenBindingEKM@CSsl3TlsContext@@IEAAKXZ`
- size: `195`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c060`
- `0x18001c490`

## callees

- `0x18001cc80`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18008bbba`
- `ntdll!RtlReleaseResource` at `0x18008bc02`
- `ntdll!RtlReleaseResource` at `0x18008bc56`
- `ntdll!RtlReleaseResource` at `0x18008bbba`
- `ntdll!RtlReleaseResource` at `0x18008bc02`
- `ntdll!RtlReleaseResource` at `0x18008bc56`
- `ntdll!RtlAcquireResourceShared` at `0x18008bb9f`
- `ntdll!RtlAcquireResourceShared` at `0x18008bb9f`
- `ncrypt!SslExportKeyingMaterial` at `0x18008bc42`
- `ncrypt!SslExportKeyingMaterial` at `0x18008bc42`

## string_xrefs

- `0x18008bc21`: `EXPORTER-Token-Binding`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::SetTokenBindingEKM(CSsl3TlsContext *this)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rcx
  _BYTE *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rbp
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rax

  if ( !*((_QWORD *)this + 318) )
    return 6;
  v9 = *((_QWORD *)this + 14);
  if ( !v9 )
    return 1359;
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v9 + 40) + 80LL), 1u);
  v10 = *((_QWORD *)this + 14);
  v11 = *(_QWORD *)(v10 + 32);
  if ( !v11 )
  {
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v10 + 40) + 80LL));
    return 6;
  }
  v8 = 32;
  v12 = (*(__int64 (__fastcall **)(CSsl3TlsContext *, __int64))(*(_QWORD *)this + 8LL))(this, 32);
  if ( !v12 )
  {
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
    return 14;
  }
  v3 = (__int64 *)*((_QWORD *)this + 1);
  if ( v3 )
    v4 = *v3;
  else
    v4 = 0;
  v13 = SslExportKeyingMaterial(v4, v11, "EXPORTER-Token-Binding", (char *)this + 1992, 64, 0, 0, v12, 32, 0);
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
  if ( v13 )
    goto LABEL_23;
  v14 = *((_QWORD *)this + 319);
  if ( v14 )
  {
    v5 = *(_BYTE **)(v14 + 8);
    if ( v5 )
    {
      v6 = 32;
      do
      {
        *v5++ = 0;
        --v6;
      }
      while ( v6 );
      (*(void (__fastcall **)(CSsl3TlsContext *, _QWORD))(*(_QWORD *)this + 16LL))(
        this,
        *(_QWORD *)(*((_QWORD *)this + 319) + 8LL));
    }
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(CSsl3TlsContext *, __int64))(*(_QWORD *)this + 8LL))(this, 16);
    *((_QWORD *)this + 319) = v15;
    if ( !v15 )
    {
      v13 = 14;
LABEL_23:
      v7 = (_BYTE *)v12;
      do
      {
        *v7++ = 0;
        --v8;
      }
      while ( v8 );
      (*(void (__fastcall **)(CSsl3TlsContext *, __int64))(*(_QWORD *)this + 16LL))(this, v12);
      return v13;
    }
  }
  **((_DWORD **)this + 319) = 32;
  *(_QWORD *)(*((_QWORD *)this + 319) + 8LL) = v12;
  return v13;
}

```

## disassembly

```asm
0x18001cc80  push    rbx
0x18001cc82  sub     rsp, 50h
0x18001cc86  cmp     qword ptr [rcx+9F0h], 0
0x18001cc8e  mov     rbx, rcx
0x18001cc91  jnz     loc_18001CD2C
0x18001cc97  mov     eax, 6
0x18001cc9c  add     rsp, 50h
0x18001cca0  pop     rbx
0x18001cca1  retn
0x18001cca2  mov     rax, [rbx+8]
0x18001cca6  test    rax, rax
0x18001cca9  jz      short loc_18001CCB5
0x18001ccab  mov     rcx, [rax]
0x18001ccae  xor     eax, eax
0x18001ccb0  jmp     loc_18008BC12
0x18001ccb5  mov     rcx, rax
0x18001ccb8  jmp     loc_18008BC12
0x18001ccbd  mov     byte ptr [rax], 0
0x18001ccc0  lea     rax, [rax+1]
0x18001ccc4  sub     rcx, 1
0x18001ccc8  jnz     short loc_18001CCBD
0x18001ccca  mov     rax, [rbx]
0x18001cccd  mov     rcx, rbx
0x18001ccd0  mov     rdx, [rbx+9F8h]
0x18001ccd7  mov     rax, [rax+10h]
0x18001ccdb  mov     rdx, [rdx+8]
0x18001ccdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce4  mov     rax, [rbx+9F8h]
0x18001cceb  mov     [rax], edi
0x18001cced  mov     rax, [rbx+9F8h]
0x18001ccf4  mov     [rax+8], rbp
0x18001ccf8  mov     eax, esi
0x18001ccfa  mov     rbp, [rsp+58h+arg_0]
0x18001ccff  mov     rdi, [rsp+58h+arg_10]
0x18001cd04  mov     rsi, [rsp+58h+arg_8]
0x18001cd09  jmp     short loc_18001CC9C
0x18001cd0b  mov     byte ptr [rax], 0
0x18001cd0e  lea     rax, [rax+1]
0x18001cd12  sub     rdi, 1
0x18001cd16  jnz     short loc_18001CD0B
0x18001cd18  mov     rax, [rbx]
0x18001cd1b  mov     rdx, rbp
0x18001cd1e  mov     rcx, rbx
0x18001cd21  mov     rax, [rax+10h]
0x18001cd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2a  jmp     short loc_18001CCF8
0x18001cd2c  mov     rcx, [rcx+70h]
0x18001cd30  test    rcx, rcx
0x18001cd33  jnz     loc_18008BB90
0x18001cd39  mov     eax, 54Fh
0x18001cd3e  jmp     loc_18001CC9C
0x18008bb90  mov     rcx, [rcx+28h]
0x18008bb94  mov     dl, 1; Wait
0x18008bb96  add     rcx, 50h ; 'P'; Resource
0x18008bb9a  mov     [rsp+58h+arg_8], rsi
0x18008bb9f  call    cs:__imp_RtlAcquireResourceShared
0x18008bba5  mov     rcx, [rbx+70h]
0x18008bba9  mov     rsi, [rcx+20h]
0x18008bbad  test    rsi, rsi
0x18008bbb0  jnz     short loc_18008BBCA
0x18008bbb2  mov     rcx, [rcx+28h]
0x18008bbb6  add     rcx, 50h ; 'P'; Resource
0x18008bbba  call    cs:__imp_RtlReleaseResource
0x18008bbc0  mov     eax, 6
0x18008bbc5  jmp     loc_18001CD04
0x18008bbca  mov     rax, [rbx]
0x18008bbcd  mov     rcx, rbx
0x18008bbd0  mov     [rsp+58h+arg_0], rbp
0x18008bbd5  mov     [rsp+58h+arg_10], rdi
0x18008bbda  mov     edi, 20h ; ' '
0x18008bbdf  mov     edx, edi
0x18008bbe1  mov     rax, [rax+8]
0x18008bbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bbea  mov     rbp, rax
0x18008bbed  test    rax, rax
0x18008bbf0  jnz     loc_18001CCA2
0x18008bbf6  mov     rax, [rbx+70h]
0x18008bbfa  mov     rcx, [rax+28h]
0x18008bbfe  add     rcx, 50h ; 'P'; Resource
0x18008bc02  call    cs:__imp_RtlReleaseResource
0x18008bc08  mov     eax, 0Eh
0x18008bc0d  jmp     loc_18001CCFA
0x18008bc12  mov     [rsp+58h+var_10], eax
0x18008bc16  lea     r9, [rbx+7C8h]
0x18008bc1d  mov     [rsp+58h+var_18], edi
0x18008bc21  lea     r8, aExporterTokenB; "EXPORTER-Token-Binding"
0x18008bc28  mov     [rsp+58h+var_20], rbp
0x18008bc2d  mov     rdx, rsi
0x18008bc30  mov     [rsp+58h+var_28], ax
0x18008bc35  mov     [rsp+58h+var_30], rax
0x18008bc3a  mov     [rsp+58h+var_38], 40h ; '@'
0x18008bc42  call    cs:__imp_SslExportKeyingMaterial
0x18008bc48  mov     rcx, [rbx+70h]
0x18008bc4c  mov     esi, eax
0x18008bc4e  mov     rcx, [rcx+28h]
0x18008bc52  add     rcx, 50h ; 'P'; Resource
0x18008bc56  call    cs:__imp_RtlReleaseResource
0x18008bc5c  test    esi, esi
0x18008bc5e  jnz     short loc_18008BC95
0x18008bc60  mov     rax, [rbx+9F8h]
0x18008bc67  test    rax, rax
0x18008bc6a  jnz     short loc_18008BC9D
0x18008bc6c  mov     rax, [rbx]
0x18008bc6f  mov     edx, 10h
0x18008bc74  mov     rcx, rbx
0x18008bc77  mov     rax, [rax+8]
0x18008bc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc80  mov     [rbx+9F8h], rax
0x18008bc87  test    rax, rax
0x18008bc8a  jnz     loc_18001CCE4
0x18008bc90  mov     esi, 0Eh
0x18008bc95  mov     rax, rbp
0x18008bc98  jmp     loc_18001CD0B
0x18008bc9d  mov     rax, [rax+8]
0x18008bca1  test    rax, rax
0x18008bca4  jz      loc_18001CCE4
0x18008bcaa  mov     rcx, rdi
0x18008bcad  jmp     loc_18001CCBD
```
