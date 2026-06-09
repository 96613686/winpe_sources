# DllRegisterServer

- ea: `0x180075ba0`
- end: `0x180075bf5`
- name: `DllRegisterServer`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180075ba0`
- `0x180075d04`
- `0x180086010`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT v0; // ebx
  __int64 v1; // rsi
  __int64 v2; // rdi
  int CLSIDRegKey; // eax
  int v4; // eax

  v0 = 0;
  v1 = 0;
  v2 = 0;
  do
  {
    CLSIDRegKey = CreateCLSIDRegKey(
                    *(unsigned int **)((char *)&g_ComClassTemplates + v2),
                    *(const BYTE **)((char *)&g_ComClassTemplates + v2 + 32));
    if ( CLSIDRegKey < 0 )
      v0 = CLSIDRegKey;
    v4 = (*(__int64 (__fastcall **)(__int64))((char *)&g_ComClassTemplates + v2 + 24))(1);
    v2 += 40;
    if ( v4 < 0 )
      v0 = v4;
    ++v1;
  }
  while ( v1 != 4 );
  return v0;
}

```

## disassembly

```asm
0x180075ba0  push    rbx
0x180075ba2  push    rbp
0x180075ba3  push    rsi
0x180075ba4  push    rdi
0x180075ba5  sub     rsp, 28h
0x180075ba9  xor     ebx, ebx
0x180075bab  lea     rbp, ?g_ComClassTemplates@@3PAUCWMDSPComClassTemplate@@A; CWMDSPComClassTemplate near * g_ComClassTemplates
0x180075bb2  xor     esi, esi
0x180075bb4  xor     edi, edi
0x180075bb6  mov     rdx, [rdi+rbp+20h]
0x180075bbb  mov     rcx, [rdi+rbp]
0x180075bbf  call    CreateCLSIDRegKey
0x180075bc4  test    eax, eax
0x180075bc6  mov     ecx, 1
0x180075bcb  cmovs   ebx, eax
0x180075bce  mov     rax, [rdi+rbp+18h]
0x180075bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075bd8  test    eax, eax
0x180075bda  lea     rdi, [rdi+28h]
0x180075bde  cmovs   ebx, eax
0x180075be1  inc     rsi
0x180075be4  cmp     rsi, 4
0x180075be8  jnz     short loc_180075BB6
0x180075bea  mov     eax, ebx
0x180075bec  add     rsp, 28h
0x180075bf0  pop     rdi
0x180075bf1  pop     rsi
0x180075bf2  pop     rbp
0x180075bf3  pop     rbx
0x180075bf4  retn
```
