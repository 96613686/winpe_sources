# ParseDpiAwarenessElement(void)

- ea: `0x180012db0`
- end: `0x180012fdb`
- name: `?ParseDpiAwarenessElement@@YA?AW4DPI_MANIFEST_VALUE@@XZ`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012b40`

## callees

- `0x180012db0`

## import_xrefs

- `ntdll!isspace` at `0x180012ef0`
- `ntdll!isspace` at `0x180012f38`
- `ntdll!isspace` at `0x180012fcb`
- `ntdll!isspace` at `0x180012ef0`
- `ntdll!isspace` at `0x180012f38`
- `ntdll!isspace` at `0x180012fcb`
- `ntdll!RtlFreeHeap` at `0x180012faf`
- `ntdll!RtlFreeHeap` at `0x180012faf`
- `ntdll!RtlAllocateHeap` at `0x180012e2d`
- `ntdll!RtlAllocateHeap` at `0x180012e2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012f67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012f67`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x180012df8`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x180012e60`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x180012df8`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x180012e60`

## string_xrefs

- `0x180012de1`: `http://schemas.microsoft.com/SMI/2016/WindowsSettings`
- `0x180012e4b`: `http://schemas.microsoft.com/SMI/2016/WindowsSettings`

## pseudocode

```c
__int64 ParseDpiAwarenessElement()
{
  unsigned int v0; // r15d
  WCHAR *pvBuffer; // rdi
  int v3; // ebx
  int v4; // ecx
  int v5; // r14d
  int v6; // esi
  const WCHAR *v7; // r13
  unsigned int i; // r14d
  int v9; // ecx
  int v10; // r14d
  int v11; // eax
  LPCWCH lpString1; // [rsp+40h] [rbp-39h]
  _DWORD v13[2]; // [rsp+48h] [rbp-31h]
  const wchar_t *v14; // [rsp+50h] [rbp-29h]
  int v15; // [rsp+58h] [rbp-21h]
  const wchar_t *v16; // [rsp+60h] [rbp-19h]
  int v17; // [rsp+68h] [rbp-11h]
  const wchar_t *v18; // [rsp+70h] [rbp-9h]
  int v19; // [rsp+78h] [rbp-1h]
  const wchar_t *v20; // [rsp+80h] [rbp+7h]
  int v21; // [rsp+88h] [rbp+Fh]
  SIZE_T pdwWrittenOrRequired; // [rsp+E0h] [rbp+67h] BYREF

  pdwWrittenOrRequired = 0;
  v0 = 0;
  QueryActCtxSettingsW(
    0,
    0,
    L"http://schemas.microsoft.com/SMI/2016/WindowsSettings",
    L"dpiAwareness",
    0,
    0,
    &pdwWrittenOrRequired);
  if ( pdwWrittenOrRequired )
  {
    pvBuffer = (WCHAR *)RtlAllocateHeap(pUserHeap, 8u, 2 * pdwWrittenOrRequired);
    if ( pvBuffer )
    {
      if ( QueryActCtxSettingsW(
             0,
             0,
             L"http://schemas.microsoft.com/SMI/2016/WindowsSettings",
             L"dpiAwareness",
             pvBuffer,
             pdwWrittenOrRequired,
             0) )
      {
        v0 = 1;
        v3 = 0;
        lpString1 = L"unaware";
        v13[0] = 2;
        v14 = L"system";
        v16 = L"permonitor";
        v18 = L"permonitorv2";
        v20 = L"uniform";
        v15 = 3;
        v17 = 4;
        v19 = 5;
        v21 = 6;
        if ( *pvBuffer )
        {
          do
          {
            if ( v0 != 1 )
              break;
            while ( isspace(pvBuffer[v3]) )
              ++v3;
            v4 = v3;
            v5 = v3;
            v6 = 0;
            v7 = &pvBuffer[v3];
            if ( *v7 != 44 )
            {
              do
              {
                if ( !pvBuffer[v3] )
                  break;
                ++v3;
                ++v6;
              }
              while ( pvBuffer[v3] != 44 );
              if ( v6 > 0 )
              {
                if ( isspace(pvBuffer[v6 - 1 + v4]) )
                {
                  v10 = v5 - 1;
                  do
                    v11 = v10 + v6--;
                  while ( isspace(pvBuffer[v11 - 1]) );
                }
                for ( i = 0; i < 5; ++i )
                {
                  if ( CompareStringOrdinal(*(LPCWCH *)&v13[4 * i - 2], -1, v7, v6, 1) == 2 && v13[4 * i] != 6 )
                  {
                    v0 = v13[4 * i];
                    break;
                  }
                }
              }
            }
            v9 = v3 + 1;
            if ( pvBuffer[v3] != 44 )
              v9 = v3;
            v3 = v9;
          }
          while ( pvBuffer[v9] );
        }
      }
      RtlFreeHeap(pUserHeap, 0, pvBuffer);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180012db0  push    rbp
0x180012db2  push    rbx
0x180012db3  push    rsi
0x180012db4  push    rdi
0x180012db5  push    r12
0x180012db7  push    r13
0x180012db9  push    r14
0x180012dbb  push    r15
0x180012dbd  lea     rbp, [rsp-1Fh]
0x180012dc2  sub     rsp, 98h
0x180012dc9  xor     r12d, r12d
0x180012dcc  lea     rax, [rbp+57h+arg_0]
0x180012dd0  mov     [rsp+0D0h+pdwWrittenOrRequired], rax; pdwWrittenOrRequired
0x180012dd5  lea     r9, settingName; "dpiAwareness"
0x180012ddc  mov     [rsp+0D0h+dwBuffer], r12; dwBuffer
0x180012de1  lea     r8, settingsNameSpace; "http://schemas.microsoft.com/SMI/2016/W"...
0x180012de8  xor     edx, edx; hActCtx
0x180012dea  mov     [rsp+0D0h+pvBuffer], r12; pvBuffer
0x180012def  xor     ecx, ecx; dwFlags
0x180012df1  mov     [rbp+57h+arg_0], r12
0x180012df5  mov     r15d, r12d
0x180012df8  call    cs:__imp_QueryActCtxSettingsW
0x180012dfe  mov     r8, [rbp+57h+arg_0]
0x180012e02  test    r8, r8
0x180012e05  jnz     short loc_180012E1E
0x180012e07  mov     eax, r15d
0x180012e0a  add     rsp, 98h
0x180012e11  pop     r15
0x180012e13  pop     r14
0x180012e15  pop     r13
0x180012e17  pop     r12
0x180012e19  pop     rdi
0x180012e1a  pop     rsi
0x180012e1b  pop     rbx
0x180012e1c  pop     rbp
0x180012e1d  retn
0x180012e1e  mov     rcx, cs:pUserHeap; HeapHandle
0x180012e25  add     r8, r8; Size
0x180012e28  mov     edx, 8; Flags
0x180012e2d  call    cs:__imp_RtlAllocateHeap
0x180012e33  mov     rdi, rax
0x180012e36  test    rax, rax
0x180012e39  jz      short loc_180012E07
0x180012e3b  mov     rax, [rbp+57h+arg_0]
0x180012e3f  lea     r9, settingName; "dpiAwareness"
0x180012e46  mov     [rsp+0D0h+pdwWrittenOrRequired], r12; pdwWrittenOrRequired
0x180012e4b  lea     r8, settingsNameSpace; "http://schemas.microsoft.com/SMI/2016/W"...
0x180012e52  mov     [rsp+0D0h+dwBuffer], rax; dwBuffer
0x180012e57  xor     edx, edx; hActCtx
0x180012e59  xor     ecx, ecx; dwFlags
0x180012e5b  mov     [rsp+0D0h+pvBuffer], rdi; pvBuffer
0x180012e60  call    cs:__imp_QueryActCtxSettingsW
0x180012e66  test    eax, eax
0x180012e68  jz      loc_180012FA3
0x180012e6e  lea     rax, aUnaware; "unaware"
0x180012e75  mov     r15d, 1
0x180012e7b  mov     ebx, r12d
0x180012e7e  mov     [rbp+57h+lpString1], rax
0x180012e82  lea     rax, aSystem_1; "system"
0x180012e89  mov     [rbp+57h+var_88], 2
0x180012e90  mov     [rbp+57h+var_80], rax
0x180012e94  lea     rax, aPermonitor; "permonitor"
0x180012e9b  mov     [rbp+57h+var_70], rax
0x180012e9f  lea     rax, aPermonitorv2; "permonitorv2"
0x180012ea6  mov     [rbp+57h+var_60], rax
0x180012eaa  lea     rax, aUniform; "uniform"
0x180012eb1  mov     [rbp+57h+var_50], rax
0x180012eb5  mov     [rbp+57h+var_78], 3
0x180012ebc  mov     [rbp+57h+var_68], 4
0x180012ec3  mov     [rbp+57h+var_58], 5
0x180012eca  mov     [rbp+57h+var_48], 6
0x180012ed1  cmp     [rdi], r12w
0x180012ed5  jz      loc_180012FA3
0x180012edb  cmp     r15d, 1
0x180012edf  jnz     loc_180012FA3
0x180012ee5  jmp     short loc_180012EE9
0x180012ee7  inc     ebx
0x180012ee9  movsxd  rax, ebx
0x180012eec  movzx   ecx, word ptr [rdi+rax*2]; C
0x180012ef0  call    cs:__imp_isspace
0x180012ef6  test    eax, eax
0x180012ef8  jnz     short loc_180012EE7
0x180012efa  movsxd  rax, ebx
0x180012efd  mov     ecx, ebx
0x180012eff  mov     r14d, ebx
0x180012f02  mov     esi, r12d
0x180012f05  lea     r13, [rdi+rax*2]
0x180012f09  cmp     word ptr [r13+0], 2Ch ; ','
0x180012f0f  jz      short loc_180012F87
0x180012f11  movsxd  rax, ebx
0x180012f14  cmp     [rdi+rax*2], r12w
0x180012f19  jz      short loc_180012F29
0x180012f1b  inc     ebx
0x180012f1d  inc     esi
0x180012f1f  movsxd  rax, ebx
0x180012f22  cmp     word ptr [rdi+rax*2], 2Ch ; ','
0x180012f27  jnz     short loc_180012F11
0x180012f29  test    esi, esi
0x180012f2b  jle     short loc_180012F87
0x180012f2d  lea     eax, [rsi+rcx]
0x180012f30  movsxd  rcx, eax
0x180012f33  movzx   ecx, word ptr [rdi+rcx*2-2]; C
0x180012f38  call    cs:__imp_isspace
0x180012f3e  test    eax, eax
0x180012f40  jnz     short loc_180012FBA
0x180012f42  mov     r14d, r12d
0x180012f45  cmp     r14d, 5
0x180012f49  jnb     short loc_180012F84
0x180012f4b  movsxd  r12, r14d
0x180012f4e  mov     r9d, esi; cchCount2
0x180012f51  add     r12, r12
0x180012f54  mov     dword ptr [rsp+0D0h+pvBuffer], 1; bIgnoreCase
0x180012f5c  mov     r8, r13; lpString2
0x180012f5f  or      edx, 0FFFFFFFFh; cchCount1
0x180012f62  mov     rcx, [rbp+r12*8+57h+lpString1]; lpString1
0x180012f67  call    cs:__imp_CompareStringOrdinal
0x180012f6d  cmp     eax, 2
0x180012f70  jz      short loc_180012F77
0x180012f72  inc     r14d
0x180012f75  jmp     short loc_180012F45
0x180012f77  cmp     [rbp+r12*8+57h+var_88], 6
0x180012f7d  jz      short loc_180012F72
0x180012f7f  mov     r15d, [rbp+r12*8+57h+var_88]
0x180012f84  xor     r12d, r12d
0x180012f87  movsxd  rax, ebx
0x180012f8a  lea     ecx, [rbx+1]
0x180012f8d  cmp     word ptr [rdi+rax*2], 2Ch ; ','
0x180012f92  cmovnz  ecx, ebx
0x180012f95  movsxd  rbx, ecx
0x180012f98  cmp     [rdi+rbx*2], r12w
0x180012f9d  jnz     loc_180012EDB
0x180012fa3  mov     rcx, cs:pUserHeap; HeapHandle
0x180012faa  mov     r8, rdi; P
0x180012fad  xor     edx, edx; Flags
0x180012faf  call    cs:__imp_RtlFreeHeap
0x180012fb5  jmp     loc_180012E07
0x180012fba  dec     r14d
0x180012fbd  lea     eax, [r14+rsi]
0x180012fc1  dec     esi
0x180012fc3  movsxd  rcx, eax
0x180012fc6  movzx   ecx, word ptr [rdi+rcx*2-2]; C
0x180012fcb  call    cs:__imp_isspace
0x180012fd1  test    eax, eax
0x180012fd3  jz      loc_180012F42
0x180012fd9  jmp     short loc_180012FBD
```
