# DllMain

- ea: `0x180005ca0`
- end: `0x180005e0e`
- name: `DllMain`
- size: `366`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001714`

## callees

- `0x180005418`
- `0x180005ca0`
- `0x180014b70`
- `0x18001d010`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x180005d57`
- `KERNEL32!ReleaseActCtx` at `0x180005d57`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HINSTANCE v3; // rsi
  BOOL v4; // edi
  void (__fastcall **v5)(HINSTANCE, _QWORD, LPVOID); // rbx
  __int64 *v6; // rbx
  __int64 *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  void (__fastcall *v10)(_QWORD); // rax
  __int64 *v11; // rbx
  __int64 *v12; // rax

  v3 = hinstDLL;
  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      v5 = (void (__fastcall **)(HINSTANCE, _QWORD, LPVOID))&off_18002E000;
      if ( &off_18002E000 != (_UNKNOWN *)-1LL )
      {
        qword_18002E9B8 = (__int64)&off_18002E000;
        if ( off_18002E000 )
        {
          do
          {
            LOBYTE(hinstDLL) = 1;
            v5[8](hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
            v5 += 9;
          }
          while ( *v5 );
        }
      }
      v6 = off_18002E100[0];
      v7 = off_18002E108;
      while ( v6 < v7 )
      {
        if ( *v6 )
        {
          LOBYTE(hinstDLL) = 1;
          (*(void (__fastcall **)(HINSTANCE))(*v6 + 64))(hinstDLL);
          v7 = off_18002E108;
        }
        ++v6;
      }
      g_hInstDLL = v3;
      return SHFusionInitializeFromModuleID(v3, 0x32u);
    }
  }
  else
  {
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( qword_18002E9D8 )
      qword_18002E9D8 = (HMODULE)-1LL;
    v8 = (_QWORD *)qword_18002E9B8;
    if ( qword_18002E9B8 )
    {
      while ( *v8 )
      {
        v9 = v8[4];
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v10 = (void (__fastcall *)(_QWORD))v8[8];
        v8[4] = 0;
        v10(0);
        v8 += 9;
      }
    }
    v11 = off_18002E100[0];
    v12 = off_18002E108;
    while ( v11 < v12 )
    {
      *(_QWORD *)&fdwReason = *v11;
      if ( *v11 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)&fdwReason + 64LL))(0);
        v12 = off_18002E108;
      }
      ++v11;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module, fdwReason);
  }
  return v4;
}

```

## disassembly

```asm
0x180005ca0  mov     [rsp+arg_0], rbx
0x180005ca5  mov     [rsp+arg_8], rsi
0x180005caa  push    rdi
0x180005cab  sub     rsp, 20h
0x180005caf  mov     rsi, rcx
0x180005cb2  mov     edi, 1
0x180005cb7  test    edx, edx
0x180005cb9  jz      loc_180005D4A
0x180005cbf  cmp     edx, edi
0x180005cc1  jnz     loc_180005DFC
0x180005cc7  lea     rbx, off_18002E000
0x180005cce  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005cd2  jz      short loc_180005CFB
0x180005cd4  cmp     cs:off_18002E000, 0
0x180005cdc  mov     cs:qword_18002E9B8, rbx
0x180005ce3  jz      short loc_180005CFB
0x180005ce5  mov     rax, [rbx+40h]
0x180005ce9  mov     cl, dil
0x180005cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf1  lea     rbx, [rbx+48h]
0x180005cf5  cmp     qword ptr [rbx], 0
0x180005cf9  jnz     short loc_180005CE5
0x180005cfb  mov     rbx, cs:off_18002E100
0x180005d02  mov     rax, cs:off_18002E108
0x180005d09  jmp     short loc_180005D2A
0x180005d0b  mov     rdx, [rbx]
0x180005d0e  test    rdx, rdx
0x180005d11  jz      short loc_180005D26
0x180005d13  mov     rax, [rdx+40h]
0x180005d17  mov     cl, dil
0x180005d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1f  mov     rax, cs:off_18002E108
0x180005d26  add     rbx, 8
0x180005d2a  cmp     rbx, rax
0x180005d2d  jb      short loc_180005D0B
0x180005d2f  mov     edx, 32h ; '2'
0x180005d34  mov     cs:?g_hInstDLL@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hInstDLL
0x180005d3b  mov     rcx, rsi; hModule
0x180005d3e  call    SHFusionInitializeFromModuleID
0x180005d43  mov     edi, eax
0x180005d45  jmp     loc_180005DFC
0x180005d4a  mov     rcx, cs:g_hActCtx; hActCtx
0x180005d51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005d55  jz      short loc_180005D68
0x180005d57  call    cs:__imp_ReleaseActCtx
0x180005d5d  mov     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180005d68  cmp     cs:qword_18002E9D8, 0
0x180005d70  jz      short loc_180005D7D
0x180005d72  mov     cs:qword_18002E9D8, 0FFFFFFFFFFFFFFFFh
0x180005d7d  mov     rbx, cs:qword_18002E9B8
0x180005d84  test    rbx, rbx
0x180005d87  jz      short loc_180005DBD
0x180005d89  jmp     short loc_180005DB7
0x180005d8b  mov     rcx, [rbx+20h]
0x180005d8f  test    rcx, rcx
0x180005d92  jz      short loc_180005DA0
0x180005d94  mov     rax, [rcx]
0x180005d97  mov     rax, [rax+10h]
0x180005d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da0  mov     rax, [rbx+40h]
0x180005da4  xor     ecx, ecx
0x180005da6  mov     qword ptr [rbx+20h], 0
0x180005dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db3  add     rbx, 48h ; 'H'
0x180005db7  cmp     qword ptr [rbx], 0
0x180005dbb  jnz     short loc_180005D8B
0x180005dbd  mov     rbx, cs:off_18002E100
0x180005dc4  mov     rax, cs:off_18002E108
0x180005dcb  jmp     short loc_180005DEB
0x180005dcd  mov     rdx, [rbx]
0x180005dd0  test    rdx, rdx
0x180005dd3  jz      short loc_180005DE7
0x180005dd5  mov     rax, [rdx+40h]
0x180005dd9  xor     ecx, ecx
0x180005ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de0  mov     rax, cs:off_18002E108
0x180005de7  add     rbx, 8
0x180005deb  cmp     rbx, rax
0x180005dee  jb      short loc_180005DCD
0x180005df0  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x180005df7  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180005dfc  mov     rbx, [rsp+28h+arg_0]
0x180005e01  mov     eax, edi
0x180005e03  mov     rsi, [rsp+28h+arg_8]
0x180005e08  add     rsp, 20h
0x180005e0c  pop     rdi
0x180005e0d  retn
```
