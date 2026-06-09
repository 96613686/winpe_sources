# DllGetClassObject

- ea: `0x180007580`
- end: `0x180007679`
- name: `DllGetClassObject`
- size: `249`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001174`
- `0x180007580`
- `0x18000b13c`
- `0x18000d010`

## string_xrefs

- `0x180007612`: `DllGetClassObject`
- `0x180007655`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v5; // ebx
  int v6; // r8d
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // eax

  if ( !ppv )
  {
    v5 = -2147024809;
    v6 = 132;
LABEL_10:
    SdpDebugTrace(1u, L"DllGetClassObject", v6, v5);
    return v5;
  }
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_CSDiagSchd != *(_OWORD *)rclsid )
  {
    v5 = -2147467259;
    v6 = 137;
    goto LABEL_10;
  }
  v7 = operator new(0x10u);
  v8 = v7;
  if ( !v7 )
  {
    v5 = -2147024882;
    v6 = 141;
    goto LABEL_10;
  }
  v7[2] = 1;
  *(_QWORD *)v7 = &CSDiagSchdFactory::`vftable';
  _InterlockedIncrement(&g_Count);
  v9 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  v5 = v9;
  if ( v9 < 0 )
    SdpDebugTrace(1u, L"DllGetClassObject", 144, v9);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v5;
}

```

## disassembly

```asm
0x180007580  mov     [rsp+arg_0], rbx
0x180007585  mov     [rsp+arg_8], rsi
0x18000758a  push    rdi
0x18000758b  sub     rsp, 20h
0x18000758f  mov     rbx, r8
0x180007592  mov     rsi, rdx
0x180007595  test    r8, r8
0x180007598  jnz     short loc_1800075AA
0x18000759a  mov     ebx, 80070057h
0x18000759f  mov     r8d, 84h
0x1800075a5  jmp     loc_180007652
0x1800075aa  and     qword ptr [r8], 0
0x1800075ae  mov     rax, qword ptr cs:CLSID_CSDiagSchd.Data1
0x1800075b5  cmp     rax, [rcx]
0x1800075b8  jnz     loc_180007647
0x1800075be  mov     rax, qword ptr cs:CLSID_CSDiagSchd.Data4
0x1800075c5  cmp     rax, [rcx+8]
0x1800075c9  jnz     short loc_180007647
0x1800075cb  mov     ecx, 10h; Size
0x1800075d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075d5  mov     rdi, rax
0x1800075d8  test    rax, rax
0x1800075db  jz      short loc_18000763A
0x1800075dd  lea     rax, ??_7CSDiagSchdFactory@@6B@; const CSDiagSchdFactory::`vftable'
0x1800075e4  mov     dword ptr [rdi+8], 1
0x1800075eb  mov     [rdi], rax
0x1800075ee  lock inc cs:?g_Count@@3JA; long g_Count
0x1800075f5  mov     rax, [rdi]
0x1800075f8  mov     r8, rbx
0x1800075fb  mov     rdx, rsi
0x1800075fe  mov     rcx, rdi
0x180007601  mov     rax, [rax]
0x180007604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007609  mov     ebx, eax
0x18000760b  test    eax, eax
0x18000760d  jns     short loc_180007629
0x18000760f  mov     r9d, eax; int
0x180007612  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180007619  mov     r8d, 90h; int
0x18000761f  mov     ecx, 1; Level
0x180007624  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007629  mov     rcx, [rdi]
0x18000762c  mov     rax, [rcx+10h]
0x180007630  mov     rcx, rdi
0x180007633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007638  jmp     short loc_180007666
0x18000763a  mov     ebx, 8007000Eh
0x18000763f  mov     r8d, 8Dh
0x180007645  jmp     short loc_180007652
0x180007647  mov     ebx, 80004005h
0x18000764c  mov     r8d, 89h; int
0x180007652  mov     r9d, ebx; int
0x180007655  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000765c  mov     ecx, 1; Level
0x180007661  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007666  mov     rsi, [rsp+28h+arg_8]
0x18000766b  mov     eax, ebx
0x18000766d  mov     rbx, [rsp+28h+arg_0]
0x180007672  add     rsp, 20h
0x180007676  pop     rdi
0x180007677  retn
```
