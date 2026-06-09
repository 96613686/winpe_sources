# Free_StringArray(ulong *,ushort * * *)

- ea: `0x180034bd4`
- end: `0x180034c2c`
- name: `?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z`
- size: `88`
- prototype: `void __fastcall(unsigned int *, LPVOID *)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008e54`
- `0x180008ed0`
- `0x18001176c`
- `0x1800346c0`
- `0x180034840`
- `0x180034998`
- `0x1800349d0`
- `0x180034afc`
- `0x180034b88`

## callees

- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c10`

## pseudocode

```c
void __fastcall Free_StringArray(unsigned int *a1, LPVOID *a2)
{
  __int64 i; // rbp

  if ( *a2 )
  {
    for ( i = 0; (unsigned int)i < *a1; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(*((LPVOID *)*a2 + i));
      *((_QWORD *)*a2 + i) = 0;
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x180034bd4  push    rbx
0x180034bd6  push    rbp
0x180034bd7  push    rsi
0x180034bd8  push    rdi
0x180034bd9  sub     rsp, 28h
0x180034bdd  cmp     qword ptr [rdx], 0
0x180034be1  mov     rdi, rdx
0x180034be4  mov     rsi, rcx
0x180034be7  jz      short loc_180034C1D
0x180034be9  xor     ebp, ebp
0x180034beb  cmp     [rcx], ebp
0x180034bed  jbe     short loc_180034C0D
0x180034bef  mov     rcx, [rdi]
0x180034bf2  mov     rcx, [rcx+rbp*8]; pv
0x180034bf6  call    cs:__imp_CoTaskMemFree
0x180034bfc  mov     rax, [rdi]
0x180034bff  mov     qword ptr [rax+rbp*8], 0
0x180034c07  inc     ebp
0x180034c09  cmp     ebp, [rsi]
0x180034c0b  jb      short loc_180034BEF
0x180034c0d  mov     rcx, [rdi]; pv
0x180034c10  call    cs:__imp_CoTaskMemFree
0x180034c16  mov     qword ptr [rdi], 0
0x180034c1d  mov     dword ptr [rsi], 0
0x180034c23  add     rsp, 28h
0x180034c27  pop     rdi
0x180034c28  pop     rsi
0x180034c29  pop     rbp
0x180034c2a  pop     rbx
0x180034c2b  retn
```
