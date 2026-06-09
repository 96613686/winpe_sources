# DllUnregisterServer

- ea: `0x180075c00`
- end: `0x180075c4d`
- name: `DllUnregisterServer`
- size: `77`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180075c00`
- `0x180075f44`
- `0x180079710`
- `0x180086010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // edi
  __int64 i; // rsi
  LSTATUS v2; // eax
  int v3; // eax

  v0 = 0;
  for ( i = 0; i != 4; ++i )
  {
    v2 = DeleteCLSIDRegKey((unsigned int *)*(&g_ComClassTemplates + 5 * i));
    if ( v2 < 0 )
      v0 = v2;
    v3 = (*(&funcs_180075C2E + 5 * i))(0);
    if ( v3 < 0 )
      v0 = v3;
  }
  return v0;
}

```

## disassembly

```asm
0x180075c00  push    rbx
0x180075c02  push    rsi
0x180075c03  push    rdi
0x180075c04  push    r14
0x180075c06  sub     rsp, 28h
0x180075c0a  xor     edi, edi
0x180075c0c  lea     r14, ?g_ComClassTemplates@@3PAUCWMDSPComClassTemplate@@A; CWMDSPComClassTemplate near * g_ComClassTemplates
0x180075c13  xor     esi, esi
0x180075c15  lea     rbx, [rsi+rsi*4]
0x180075c19  mov     rcx, [r14+rbx*8]
0x180075c1d  call    DeleteCLSIDRegKey
0x180075c22  test    eax, eax
0x180075c24  cmovs   edi, eax
0x180075c27  mov     rax, (funcs_180075C2E - 1801B6940h)[r14+rbx*8]
0x180075c2c  xor     ecx, ecx; int
0x180075c2e  call    _guard_dispatch_icall$thunk$10345483385596137414; WMALFXAPORegister(int) ...
0x180075c33  test    eax, eax
0x180075c35  cmovs   edi, eax
0x180075c38  inc     rsi
0x180075c3b  cmp     rsi, 4
0x180075c3f  jnz     short loc_180075C15
0x180075c41  mov     eax, edi
0x180075c43  add     rsp, 28h
0x180075c47  pop     r14
0x180075c49  pop     rdi
0x180075c4a  pop     rsi
0x180075c4b  pop     rbx
0x180075c4c  retn
```
