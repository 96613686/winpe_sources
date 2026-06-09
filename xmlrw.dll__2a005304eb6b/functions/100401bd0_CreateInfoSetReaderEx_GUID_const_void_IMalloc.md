# CreateInfoSetReaderEx(_GUID const &,void * *,IMalloc *)

- ea: `0x100401bd0`
- end: `0x100401dfe`
- name: `?CreateInfoSetReaderEx@@YAJAEBU_GUID@@PEAPEAXPEAUIMalloc@@@Z`
- size: `558`
- prototype: `int(const struct _GUID *, void **, struct IMalloc *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100401bc0`

## callees

- `0x100401780`
- `0x100401bd0`
- `0x100401e10`
- `0x10040cc10`
- `0x100415950`
- `0x100416690`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100401c63`
- `KERNEL32!HeapAlloc` at `0x100401c63`
- `KERNEL32!GetTickCount` at `0x100401cb8`
- `KERNEL32!GetTickCount` at `0x100401cb8`

## pseudocode

```c
__int64 __fastcall CreateInfoSetReaderEx(const struct _GUID *a1, void **a2, struct IMalloc *a3)
{
  YReader *v6; // rax
  YReader *v7; // rdi
  struct IMalloc *v8; // rcx
  _QWORD *v9; // rax
  DWORD TickCount; // eax
  DeclDoctype *v11; // rcx
  unsigned int v12; // ebx

  *a2 = 0;
  v6 = (YReader *)Base::operator new(0x2050u, a3);
  if ( v6 )
    v7 = YReader::YReader(v6, a3);
  else
    v7 = 0;
  v8 = (struct IMalloc *)*((_QWORD *)v7 + 53);
  if ( v8 || (v8 = g_pMalloc) != 0 )
    v9 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v8->lpVtbl->Alloc)(v8, 0x2000);
  else
    v9 = HeapAlloc(g_hHeap, 0, 0x2000u);
  if ( !v9 )
  {
    MXRRaiseException(-2147024882);
    __debugbreak();
    JUMPOUT(0x100401DFELL);
  }
  *v9 = 0;
  v9[1] = 0;
  v9[2] = v9 + 4;
  v9[3] = v9 + 1024;
  *((_QWORD *)v7 + 54) = v9;
  *((_QWORD *)v7 + 55) = v9;
  *((_DWORD *)v7 + 310) = 200;
  *((_DWORD *)v7 + 311) = 100;
  TickCount = GetTickCount();
  *((_DWORD *)v7 + 308) = TickCount ^ ((TickCount ^ (TickCount << 7)) << 11);
  *((_BYTE *)v7 + 1248) = 0;
  *((_DWORD *)v7 + 132) = 0;
  NamespaceSupport::PushPrefix(
    (YReader *)((char *)v7 + 512),
    (struct StringPtr *)&CodeStringPtr::xml,
    (struct StringPtr *)&CodeStringPtr::xmlUri);
  NamespaceSupport::PushPrefix(
    (YReader *)((char *)v7 + 512),
    (struct StringPtr *)&CodeStringPtr::empty,
    (struct StringPtr *)&CodeStringPtr::empty);
  *((_DWORD *)v7 + 132) = 1;
  *((_DWORD *)v7 + 341) = 16;
  *((_DWORD *)v7 + 342) = 4;
  *((_DWORD *)v7 + 342) = 12;
  *((_DWORD *)v7 + 351) = 8;
  *((_DWORD *)v7 + 352) = 2;
  *((_DWORD *)v7 + 352) = 6;
  *((_DWORD *)v7 + 361) = 8;
  *((_DWORD *)v7 + 362) = 2;
  *((_DWORD *)v7 + 362) = 6;
  *((_DWORD *)v7 + 371) = 8;
  *((_DWORD *)v7 + 372) = 2;
  *((_DWORD *)v7 + 372) = 6;
  if ( !dword_100450848 )
    DeclDoctype::InitializeDecls(v11);
  v12 = (**((__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v7 + 2))((__int64)v7 + 16, a1, a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v7 + 2) + 16LL))((__int64)v7 + 16);
  return v12;
}

```

## disassembly

```asm
0x100401bd0  mov     [rsp+arg_0], rbx
0x100401bd5  mov     [rsp+arg_8], rsi
0x100401bda  mov     [rsp+arg_10], rdi
0x100401bdf  mov     [rsp+arg_18], r14
0x100401be4  push    r15
0x100401be6  sub     rsp, 50h
0x100401bea  mov     rbx, r8
0x100401bed  mov     rsi, rdx
0x100401bf0  mov     r14, rcx
0x100401bf3  xor     r15d, r15d
0x100401bf6  mov     [rsp+58h+var_20], r15
0x100401bfb  mov     [rdx], r15
0x100401bfe  mov     rdx, rbx; struct IMalloc *
0x100401c01  mov     ecx, 2050h; dwBytes
0x100401c06  call    ??2Base@@SAPEAX_KPEAUIMalloc@@@Z; Base::operator new(unsigned __int64,IMalloc *)
0x100401c0b  test    rax, rax
0x100401c0e  jz      short loc_100401C20
0x100401c10  mov     rdx, rbx; struct IMalloc *
0x100401c13  mov     rcx, rax; this
0x100401c16  call    ??0YReader@@QEAA@PEAUIMalloc@@@Z; YReader::YReader(IMalloc *)
0x100401c1b  mov     rdi, rax
0x100401c1e  jmp     short loc_100401C23
0x100401c20  mov     rdi, r15
0x100401c23  mov     [rsp+58h+var_20], rdi
0x100401c28  mov     rcx, [rdi+1A8h]
0x100401c2f  test    rcx, rcx
0x100401c32  jz      short loc_100401C48
0x100401c34  mov     rax, [rcx]
0x100401c37  mov     edx, 2000h
0x100401c3c  mov     rax, [rax+18h]
0x100401c40  call    cs:__guard_dispatch_icall_fptr
0x100401c46  jmp     short loc_100401C69
0x100401c48  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100401c4f  test    rcx, rcx
0x100401c52  jnz     short loc_100401C34
0x100401c54  xor     edx, edx; dwFlags
0x100401c56  mov     r8d, 2000h; dwBytes
0x100401c5c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100401c63  call    cs:__imp_HeapAlloc
0x100401c69  mov     rcx, rax
0x100401c6c  test    rax, rax
0x100401c6f  jz      loc_100401DF2
0x100401c75  mov     [rcx], r15
0x100401c78  mov     [rcx+8], r15
0x100401c7c  lea     rax, [rcx+20h]
0x100401c80  mov     [rcx+10h], rax
0x100401c84  lea     rax, [rcx+2000h]
0x100401c8b  mov     [rcx+18h], rax
0x100401c8f  mov     [rdi+1B0h], rcx
0x100401c96  mov     [rdi+1B8h], rcx
0x100401c9d  lea     rbx, [rdi+200h]
0x100401ca4  mov     dword ptr [rbx+2D8h], 0C8h
0x100401cae  mov     dword ptr [rbx+2DCh], 64h ; 'd'
0x100401cb8  call    cs:__imp_GetTickCount
0x100401cbe  mov     ecx, eax
0x100401cc0  shl     ecx, 7
0x100401cc3  xor     ecx, eax
0x100401cc5  shl     ecx, 0Bh
0x100401cc8  xor     ecx, eax
0x100401cca  mov     [rbx+2D0h], ecx
0x100401cd0  mov     byte ptr [rbx+2E0h], 0
0x100401cd7  mov     [rbx+10h], r15d
0x100401cdb  lea     r8, ?xmlUri@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100401ce2  lea     rdx, ?xml@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100401ce9  mov     rcx, rbx; this
0x100401cec  call    ?PushPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x100401cf1  lea     r8, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100401cf8  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100401cff  mov     rcx, rbx; this
0x100401d02  call    ?PushPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x100401d07  mov     dword ptr [rbx+10h], 1
0x100401d0e  mov     dword ptr [rdi+554h], 10h
0x100401d18  mov     dword ptr [rdi+558h], 4
0x100401d22  mov     dword ptr [rdi+558h], 0Ch
0x100401d2c  mov     dword ptr [rdi+57Ch], 8
0x100401d36  mov     dword ptr [rdi+580h], 2
0x100401d40  mov     dword ptr [rdi+580h], 6
0x100401d4a  mov     dword ptr [rdi+5A4h], 8
0x100401d54  mov     dword ptr [rdi+5A8h], 2
0x100401d5e  mov     dword ptr [rdi+5A8h], 6
0x100401d68  mov     dword ptr [rdi+5CCh], 8
0x100401d72  mov     dword ptr [rdi+5D0h], 2
0x100401d7c  mov     dword ptr [rdi+5D0h], 6
0x100401d86  cmp     cs:dword_100450848, 0
0x100401d8d  jnz     short loc_100401D94
0x100401d8f  call    ?InitializeDecls@DeclDoctype@@QEAAXXZ; DeclDoctype::InitializeDecls(void)
0x100401d94  lea     rcx, [rdi+10h]
0x100401d98  mov     rax, [rcx]
0x100401d9b  mov     r8, rsi
0x100401d9e  mov     rdx, r14
0x100401da1  mov     rax, [rax]
0x100401da4  call    cs:__guard_dispatch_icall_fptr
0x100401daa  mov     ebx, eax
0x100401dac  mov     [rsp+58h+var_30], eax
0x100401db0  jmp     short loc_100401DBF
0x100401db2  mov     ebx, [rsp+58h+var_38]
0x100401db6  mov     [rsp+58h+var_30], ebx
0x100401dba  mov     rdi, [rsp+58h+var_20]
0x100401dbf  test    rdi, rdi
0x100401dc2  jz      short loc_100401DD5
0x100401dc4  lea     rcx, [rdi+10h]
0x100401dc8  mov     rax, [rcx]
0x100401dcb  mov     rax, [rax+10h]
0x100401dcf  call    cs:__guard_dispatch_icall_fptr
0x100401dd5  mov     eax, ebx
0x100401dd7  mov     rbx, [rsp+58h+arg_0]
0x100401ddc  mov     rsi, [rsp+58h+arg_8]
0x100401de1  mov     rdi, [rsp+58h+arg_10]
0x100401de6  mov     r14, [rsp+58h+arg_18]
0x100401deb  add     rsp, 50h
0x100401def  pop     r15
0x100401df1  retn
0x100401df2  mov     ecx, 8007000Eh; int
0x100401df7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100401dfc  nop
0x100401dfd  int     3; Trap to Debugger
0x100439e20  push    rbp
0x100439e22  sub     rsp, 20h
0x100439e26  mov     rbp, rdx
0x100439e29  mov     [rbp+48h], rcx
0x100439e2d  mov     [rbp+40h], rcx
0x100439e31  mov     rax, [rbp+40h]
0x100439e35  mov     rcx, [rax]
0x100439e38  mov     [rbp+30h], rcx
0x100439e3c  mov     rax, [rbp+30h]
0x100439e40  mov     eax, [rax]
0x100439e42  cmp     eax, 0C0000005h
0x100439e47  jz      short loc_100439E79
0x100439e49  add     eax, 1FFFFFFFh
0x100439e4e  cmp     eax, 1
0x100439e51  ja      short loc_100439E69
0x100439e53  mov     rax, [rbp+30h]
0x100439e57  cmp     dword ptr [rax+18h], 1
0x100439e5b  jnz     short loc_100439E69
0x100439e5d  mov     rax, [rbp+30h]
0x100439e61  mov     ecx, [rax+20h]
0x100439e64  mov     [rbp+20h], ecx
0x100439e67  jmp     short loc_100439E70
0x100439e69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439e70  mov     dword ptr [rbp+24h], 1
0x100439e77  jmp     short loc_100439E80
0x100439e79  mov     dword ptr [rbp+24h], 0
0x100439e80  mov     eax, [rbp+24h]
0x100439e83  add     rsp, 20h
0x100439e87  pop     rbp
0x100439e88  retn
```
