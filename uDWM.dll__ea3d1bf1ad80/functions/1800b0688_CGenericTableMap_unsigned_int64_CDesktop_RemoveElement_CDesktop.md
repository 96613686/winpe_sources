# CGenericTableMap<unsigned __int64,CDesktop>::RemoveElement(CDesktop *)

- ea: `0x1800b0688`
- end: `0x1800b06ec`
- name: `?RemoveElement@?$CGenericTableMap@_KUCDesktop@@@@QEAAXPEAUCDesktop@@@Z`
- size: `100`
- prototype: `void __fastcall(struct _RTL_GENERIC_TABLE *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800addb0`
- `0x1800dae54`
- `0x1800dbe94`

## callees

- `0x1800b0688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b06de`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b06de`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800b06cc`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800b06cc`

## pseudocode

```c
void __fastcall CGenericTableMap<unsigned __int64,CDesktop>::RemoveElement(struct _RTL_GENERIC_TABLE *a1, _QWORD *a2)
{
  _QWORD Buffer[2]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v3; // [rsp+30h] [rbp-58h]
  __int128 v4; // [rsp+40h] [rbp-48h]
  __int128 v5; // [rsp+50h] [rbp-38h]
  __int64 v6; // [rsp+60h] [rbp-28h]
  char v7; // [rsp+68h] [rbp-20h]
  __int128 v8; // [rsp+70h] [rbp-18h]

  Buffer[1] = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v8 = 0;
  v6 = -1;
  v7 = 0;
  Buffer[0] = *a2;
  if ( !RtlDeleteElementGenericTable(a1, Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x1800b0688  mov     rax, rsp
0x1800b068b  sub     rsp, 88h
0x1800b0692  xorps   xmm0, xmm0
0x1800b0695  mov     qword ptr [rax-60h], 0
0x1800b069d  movdqa  xmmword ptr [rax-58h], xmm0
0x1800b06a2  xorps   xmm1, xmm1
0x1800b06a5  movdqa  xmmword ptr [rax-48h], xmm1
0x1800b06aa  movdqa  xmmword ptr [rax-38h], xmm0
0x1800b06af  movups  xmmword ptr [rax-18h], xmm0
0x1800b06b3  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFFh
0x1800b06bb  mov     byte ptr [rax-20h], 0
0x1800b06bf  mov     rax, [rdx]
0x1800b06c2  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800b06c7  mov     [rsp+88h+Buffer], rax
0x1800b06cc  call    cs:__imp_RtlDeleteElementGenericTable
0x1800b06d2  test    al, al
0x1800b06d4  jnz     short loc_1800B06E4
0x1800b06d6  xor     edx, edx; pContextRecord
0x1800b06d8  xor     ecx, ecx; pExceptionRecord
0x1800b06da  lea     r8d, [rdx+1]; dwFlags
0x1800b06de  call    cs:__imp_RaiseFailFastException
0x1800b06e4  add     rsp, 88h
0x1800b06eb  retn
```
