# D3DCommon::DX10Framework::GetDefaultAdapterPtr(IDXGIAdapter * *)

- ea: `0x18002d6b4`
- end: `0x18002d870`
- name: `?GetDefaultAdapterPtr@DX10Framework@D3DCommon@@SAJPEAPEAUIDXGIAdapter@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct IDXGIAdapter **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d63c`

## callees

- `0x1800151bb`
- `0x18002d6b4`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `dxgi!CreateDXGIFactory` at `0x18002d728`
- `dxgi!CreateDXGIFactory` at `0x18002d728`

## pseudocode

```c
HRESULT __fastcall D3DCommon::DX10Framework::GetDefaultAdapterPtr(struct IDXGIAdapter **a1)
{
  HRESULT result; // eax
  unsigned int v3; // r14d
  char v4; // si
  int v5; // ebx
  struct IDXGIAdapter *v6; // rcx
  struct IDXGIAdapter *v7; // [rsp+28h] [rbp-49h] BYREF
  __int64 v8; // [rsp+30h] [rbp-41h] BYREF
  void *ppFactory[2]; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v10[64]; // [rsp+48h] [rbp-29h] BYREF
  int v11; // [rsp+88h] [rbp+17h]
  int v12; // [rsp+8Ch] [rbp+1Bh]
  int v13; // [rsp+98h] [rbp+27h]

  ppFactory[1] = (void *)-2LL;
  v7 = 0;
  ppFactory[0] = 0;
  v8 = 0;
  memset_0(v10, 0, 0x60u);
  if ( !a1 )
    return -2147467261;
  result = CreateDXGIFactory(&GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369, ppFactory);
  if ( result >= 0 )
  {
    v3 = 0;
    v4 = 0;
    while ( 1 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, _QWORD, struct IDXGIAdapter **))(*(_QWORD *)ppFactory[0] + 56LL))(
             ppFactory[0],
             v3,
             &v7);
      if ( v5 < 0 )
        break;
      v5 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, _QWORD, __int64 *))v7->lpVtbl->EnumOutputs)(v7, 0, &v8);
      if ( v5 < 0 )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 56LL))(v8, v10);
      if ( v5 < 0 )
        break;
      if ( v13 && !v12 && !v11 )
      {
        *a1 = v7;
        v6 = 0;
        v7 = 0;
        v4 = 1;
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
      ((void (__fastcall *)(struct IDXGIAdapter *))v7->lpVtbl->Release)(v7);
      v7 = 0;
      ++v3;
    }
    v6 = v7;
LABEL_14:
    if ( v6 )
    {
      ((void (__fastcall *)(struct IDXGIAdapter *))v6->lpVtbl->Release)(v6);
      v7 = 0;
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
    }
    if ( ppFactory[0] )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory[0] + 16LL))(ppFactory[0]);
    if ( !v4 )
      *a1 = 0;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002d6b4  mov     rax, rsp
0x18002d6b7  push    rbp
0x18002d6b8  push    rdi
0x18002d6b9  push    r14
0x18002d6bb  lea     rbp, [rax-5Fh]
0x18002d6bf  sub     rsp, 0B0h
0x18002d6c6  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002d6ce  mov     [rax+10h], rbx
0x18002d6d2  mov     [rax+18h], rsi
0x18002d6d6  mov     rax, cs:__security_cookie
0x18002d6dd  xor     rax, rsp
0x18002d6e0  mov     [rbp+57h+var_20], rax
0x18002d6e4  mov     rdi, rcx
0x18002d6e7  mov     [rbp+57h+var_A0], 0
0x18002d6ef  mov     [rbp+57h+ppFactory], 0
0x18002d6f7  mov     [rbp+57h+var_98], 0
0x18002d6ff  xor     edx, edx; Val
0x18002d701  lea     r8d, [rdx+60h]; Size
0x18002d705  lea     rcx, [rbp+57h+var_80]; void *
0x18002d709  call    memset_0
0x18002d70e  test    rdi, rdi
0x18002d711  jnz     short loc_18002D71D
0x18002d713  mov     eax, 80004003h
0x18002d718  jmp     loc_18002D84C
0x18002d71d  lea     rdx, [rbp+57h+ppFactory]; ppFactory
0x18002d721  lea     rcx, _GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369; riid
0x18002d728  call    cs:__imp_CreateDXGIFactory
0x18002d72e  test    eax, eax
0x18002d730  js      loc_18002D84C
0x18002d736  xor     r14d, r14d
0x18002d739  xor     sil, sil
0x18002d73c  mov     rcx, [rbp+57h+ppFactory]
0x18002d740  mov     rax, [rcx]
0x18002d743  lea     r8, [rbp+57h+var_A0]
0x18002d747  mov     edx, r14d
0x18002d74a  mov     rax, [rax+38h]
0x18002d74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d753  mov     ebx, eax
0x18002d755  test    eax, eax
0x18002d757  js      loc_18002D7EF
0x18002d75d  mov     rcx, [rbp+57h+var_A0]
0x18002d761  mov     rax, [rcx]
0x18002d764  lea     r8, [rbp+57h+var_98]
0x18002d768  xor     edx, edx
0x18002d76a  mov     rax, [rax+38h]
0x18002d76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d773  mov     ebx, eax
0x18002d775  test    eax, eax
0x18002d777  js      short loc_18002D7EF
0x18002d779  mov     rcx, [rbp+57h+var_98]
0x18002d77d  mov     rax, [rcx]
0x18002d780  lea     rdx, [rbp+57h+var_80]
0x18002d784  mov     rax, [rax+38h]
0x18002d788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d78d  mov     ebx, eax
0x18002d78f  test    eax, eax
0x18002d791  js      short loc_18002D7EF
0x18002d793  cmp     [rbp+57h+var_30], 0
0x18002d797  jz      short loc_18002D7A5
0x18002d799  cmp     [rbp+57h+var_3C], 0
0x18002d79d  jnz     short loc_18002D7A5
0x18002d79f  cmp     [rbp+57h+var_40], 0
0x18002d7a3  jz      short loc_18002D7DD
0x18002d7a5  mov     rcx, [rbp+57h+var_98]
0x18002d7a9  mov     rax, [rcx]
0x18002d7ac  mov     rax, [rax+10h]
0x18002d7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7b5  mov     [rbp+57h+var_98], 0
0x18002d7bd  mov     rcx, [rbp+57h+var_A0]
0x18002d7c1  mov     rax, [rcx]
0x18002d7c4  mov     rax, [rax+10h]
0x18002d7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7cd  mov     [rbp+57h+var_A0], 0
0x18002d7d5  inc     r14d
0x18002d7d8  jmp     loc_18002D73C
0x18002d7dd  mov     rax, [rbp+57h+var_A0]
0x18002d7e1  mov     [rdi], rax
0x18002d7e4  xor     ecx, ecx
0x18002d7e6  mov     [rbp+57h+var_A0], rcx
0x18002d7ea  mov     sil, 1
0x18002d7ed  jmp     short loc_18002D7F3
0x18002d7ef  mov     rcx, [rbp+57h+var_A0]
0x18002d7f3  test    rcx, rcx
0x18002d7f6  jz      short loc_18002D80C
0x18002d7f8  mov     rax, [rcx]
0x18002d7fb  mov     rax, [rax+10h]
0x18002d7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d804  mov     [rbp+57h+var_A0], 0
0x18002d80c  mov     rcx, [rbp+57h+var_98]
0x18002d810  test    rcx, rcx
0x18002d813  jz      short loc_18002D829
0x18002d815  mov     rax, [rcx]
0x18002d818  mov     rax, [rax+10h]
0x18002d81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d821  mov     [rbp+57h+var_98], 0
0x18002d829  mov     rcx, [rbp+57h+ppFactory]
0x18002d82d  test    rcx, rcx
0x18002d830  jz      short loc_18002D83E
0x18002d832  mov     rax, [rcx]
0x18002d835  mov     rax, [rax+10h]
0x18002d839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d83e  test    sil, sil
0x18002d841  jnz     short loc_18002D84A
0x18002d843  mov     qword ptr [rdi], 0
0x18002d84a  mov     eax, ebx
0x18002d84c  mov     rcx, [rbp+57h+var_20]
0x18002d850  xor     rcx, rsp; StackCookie
0x18002d853  call    __security_check_cookie
0x18002d858  lea     r11, [rsp+0C0h+var_10]
0x18002d860  mov     rbx, [r11+28h]
0x18002d864  mov     rsi, [r11+30h]
0x18002d868  mov     rsp, r11
0x18002d86b  pop     r14
0x18002d86d  pop     rdi
0x18002d86e  pop     rbp
0x18002d86f  retn
```
