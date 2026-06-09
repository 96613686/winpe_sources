# CShareSecurityInformation::~CShareSecurityInformation(void)

- ea: `0x18000aef8`
- end: `0x18000af58`
- name: `??1CShareSecurityInformation@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CShareSecurityInformation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000abc0`

## callees

- `0x18000aef8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000af17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000af17`

## pseudocode

```c
void __fastcall CShareSecurityInformation::~CShareSecurityInformation(CShareSecurityInformation *this)
{
  struct _TP_WORK *v2; // rcx

  *(_QWORD *)this = &CShareSecurityInformation::`vftable';
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 31);
  if ( v2 )
    CloseThreadpoolWork(v2);
  CloseHandle(*((HANDLE *)this + 29));
  LocalFree(*((HLOCAL *)this + 1));
  LocalFree(*((HLOCAL *)this + 2));
  LocalFree(*((HLOCAL *)this + 32));
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x18000aef8  push    rbx
0x18000aefa  sub     rsp, 20h
0x18000aefe  lea     rax, ??_7CShareSecurityInformation@@6B@; const CShareSecurityInformation::`vftable'
0x18000af05  mov     rbx, rcx
0x18000af08  mov     [rcx], rax
0x18000af0b  mov     rcx, [rcx+0F8h]; pwk
0x18000af12  test    rcx, rcx
0x18000af15  jz      short loc_18000AF1D
0x18000af17  call    cs:__imp_CloseThreadpoolWork
0x18000af1d  mov     rcx, [rbx+0E8h]; hObject
0x18000af24  call    cs:__imp_CloseHandle
0x18000af2a  mov     rcx, [rbx+8]; hMem
0x18000af2e  call    cs:__imp_LocalFree
0x18000af34  mov     rcx, [rbx+10h]; hMem
0x18000af38  call    cs:__imp_LocalFree
0x18000af3e  mov     rcx, [rbx+100h]; hMem
0x18000af45  call    cs:__imp_LocalFree
0x18000af4b  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000af52  add     rsp, 20h
0x18000af56  pop     rbx
0x18000af57  retn
```
