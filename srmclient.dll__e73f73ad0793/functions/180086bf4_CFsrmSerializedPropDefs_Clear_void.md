# CFsrmSerializedPropDefs::Clear(void)

- ea: `0x180086bf4`
- end: `0x180086c82`
- name: `?Clear@CFsrmSerializedPropDefs@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(CFsrmSerializedPropDefs *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180087908`
- `0x180099108`
- `0x180099120`
- `0x18009ba9c`

## callees

- `0x180086bf4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180086c1d`
- `ole32!CoTaskMemFree` at `0x180086c3e`
- `ole32!CoTaskMemFree` at `0x180086c53`
- `ole32!CoTaskMemFree` at `0x180086c63`
- `ole32!CoTaskMemFree` at `0x180086c1d`
- `ole32!CoTaskMemFree` at `0x180086c3e`
- `ole32!CoTaskMemFree` at `0x180086c53`
- `ole32!CoTaskMemFree` at `0x180086c63`

## pseudocode

```c
void __fastcall CFsrmSerializedPropDefs::Clear(CFsrmSerializedPropDefs *this)
{
  unsigned int i; // esi
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 j; // r14

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *(_DWORD *)this; ++i )
    {
      v3 = *((_QWORD *)this + 1);
      v4 = 32LL * i;
      CoTaskMemFree(*(LPVOID *)(v4 + v3));
      if ( *(_QWORD *)(v4 + v3 + 16) )
      {
        for ( j = 0; (unsigned int)j < *(_DWORD *)(v4 + v3 + 12); j = (unsigned int)(j + 1) )
          CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(v4 + v3 + 16) + 8 * j));
        CoTaskMemFree(*(LPVOID *)(v4 + v3 + 16));
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 1));
    *(_DWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180086bf4  push    rbx
0x180086bf6  push    rbp
0x180086bf7  push    rsi
0x180086bf8  push    rdi
0x180086bf9  push    r14
0x180086bfb  sub     rsp, 20h
0x180086bff  cmp     qword ptr [rcx+8], 0
0x180086c04  mov     rbx, rcx
0x180086c07  jz      short loc_180086C77
0x180086c09  xor     esi, esi
0x180086c0b  cmp     [rcx], esi
0x180086c0d  jbe     short loc_180086C5F
0x180086c0f  mov     rbp, [rbx+8]
0x180086c13  mov     edi, esi
0x180086c15  shl     rdi, 5
0x180086c19  mov     rcx, [rdi+rbp]; pv
0x180086c1d  call    cs:__imp_CoTaskMemFree
0x180086c23  cmp     qword ptr [rdi+rbp+10h], 0
0x180086c29  jz      short loc_180086C59
0x180086c2b  xor     r14d, r14d
0x180086c2e  cmp     [rdi+rbp+0Ch], r14d
0x180086c33  jbe     short loc_180086C4E
0x180086c35  mov     rcx, [rdi+rbp+10h]
0x180086c3a  mov     rcx, [rcx+r14*8]; pv
0x180086c3e  call    cs:__imp_CoTaskMemFree
0x180086c44  inc     r14d
0x180086c47  cmp     r14d, [rdi+rbp+0Ch]
0x180086c4c  jb      short loc_180086C35
0x180086c4e  mov     rcx, [rdi+rbp+10h]; pv
0x180086c53  call    cs:__imp_CoTaskMemFree
0x180086c59  inc     esi
0x180086c5b  cmp     esi, [rbx]
0x180086c5d  jb      short loc_180086C0F
0x180086c5f  mov     rcx, [rbx+8]; pv
0x180086c63  call    cs:__imp_CoTaskMemFree
0x180086c69  mov     dword ptr [rbx], 0
0x180086c6f  mov     qword ptr [rbx+8], 0
0x180086c77  add     rsp, 20h
0x180086c7b  pop     r14
0x180086c7d  pop     rdi
0x180086c7e  pop     rsi
0x180086c7f  pop     rbp
0x180086c80  pop     rbx
0x180086c81  retn
```
