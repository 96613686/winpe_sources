# CloseEndpointOutsideLock<CAutoWriterLock>(CAutoWriterLock &,void * &)

- ea: `0x180008b58`
- end: `0x180008bd0`
- name: `??$CloseEndpointOutsideLock@VCAutoWriterLock@@@@YAXAEAVCAutoWriterLock@@AEAPEAX@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180005a4c`

## callees

- `0x180008b58`
- `0x180008dcc`
- `0x180024b0c`
- `0x180025850`

## import_xrefs

- `WDSSRV!WdsEndpointClose` at `0x180008ba6`
- `WDSSRV!WdsEndpointClose` at `0x180008ba6`

## pseudocode

```c
void __fastcall CloseEndpointOutsideLock<CAutoWriterLock>(__int64 a1, __int64 *a2)
{
  int v2; // eax
  __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  const char *v9; // rdx

  v2 = *(_DWORD *)(a1 + 8);
  if ( v2 )
    *(_DWORD *)(a1 + 8) = v2 + 1;
  else
    CAutoWriterLock::Lock((LPCRITICAL_SECTION *)a1);
  v5 = *a2;
  *a2 = 0;
  v6 = *(_DWORD *)(a1 + 8);
  if ( v6 )
  {
    v7 = v6 - 1;
    *(_DWORD *)(a1 + 8) = v7;
    if ( !v7 )
      CMRSWLock::WriterRelease(*(CMRSWLock **)a1);
  }
  if ( v5 )
  {
    v8 = WdsEndpointClose(v5);
    ElValidateWin32(v8, v9, "internal\\onecorebase\\inc\\wdssrv.h", 0x3F7u);
  }
}

```

## disassembly

```asm
0x180008b58  mov     [rsp+arg_0], rbx
0x180008b5d  mov     [rsp+arg_8], rsi
0x180008b62  push    rdi
0x180008b63  sub     rsp, 20h
0x180008b67  mov     eax, [rcx+8]
0x180008b6a  mov     rsi, rdx
0x180008b6d  mov     rbx, rcx
0x180008b70  test    eax, eax
0x180008b72  jnz     short loc_180008B7B
0x180008b74  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180008b79  jmp     short loc_180008B80
0x180008b7b  inc     eax
0x180008b7d  mov     [rcx+8], eax
0x180008b80  mov     rdi, [rsi]
0x180008b83  and     qword ptr [rsi], 0
0x180008b87  mov     eax, [rbx+8]
0x180008b8a  test    eax, eax
0x180008b8c  jz      short loc_180008B9E
0x180008b8e  sub     eax, 1
0x180008b91  mov     [rbx+8], eax
0x180008b94  jnz     short loc_180008B9E
0x180008b96  mov     rcx, [rbx]; this
0x180008b99  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180008b9e  test    rdi, rdi
0x180008ba1  jz      short loc_180008BC0
0x180008ba3  mov     rcx, rdi
0x180008ba6  call    cs:__imp_WdsEndpointClose
0x180008bac  mov     r9d, 3F7h; unsigned int
0x180008bb2  lea     r8, aInternalOnecor_2; "internal\\onecorebase\\inc\\wdssrv.h"
0x180008bb9  mov     ecx, eax; unsigned int
0x180008bbb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008bc0  mov     rbx, [rsp+28h+arg_0]
0x180008bc5  mov     rsi, [rsp+28h+arg_8]
0x180008bca  add     rsp, 20h
0x180008bce  pop     rdi
0x180008bcf  retn
```
