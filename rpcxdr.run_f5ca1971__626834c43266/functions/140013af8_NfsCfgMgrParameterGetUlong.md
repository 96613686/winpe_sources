# NfsCfgMgrParameterGetUlong

- ea: `0x140013af8`
- end: `0x140013b72`
- name: `NfsCfgMgrParameterGetUlong`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a2d0`
- `0x140010da8`
- `0x140012468`
- `0x140024078`
- `0x140024514`

## callees

- `0x1400122e0`
- `0x140013828`
- `0x140013af8`

## pseudocode

```c
__int64 __fastcall NfsCfgMgrParameterGetUlong(int a1, _DWORD *a2)
{
  int v3; // edi
  int v4; // esi
  __int64 v5; // rbx
  unsigned int v6; // eax
  __int64 result; // rax
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  v3 = 0;
  v4 = NfsResMgrpResourceRecordLookupAndReference(a1, &v8);
  if ( v4 >= 0 )
  {
    v5 = v8;
    if ( *(_DWORD *)(v8 + 60) )
      v4 = -1073741811;
    else
      v3 = *(_DWORD *)(v8 + 232);
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 4), 0, 0);
    if ( NfsRefHistoryTracingpGlobal )
      NfsReferenceHistoryCaptureRecord((_DWORD *)v5, v6, 1u);
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 4));
  }
  if ( v4 < 0 )
    v3 = 0;
  result = (unsigned int)v4;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x140013af8  push    rbx
0x140013afa  push    rsi
0x140013afb  push    rdi
0x140013afc  push    r14
0x140013afe  sub     rsp, 28h
0x140013b02  mov     r14, rdx
0x140013b05  mov     [rsp+48h+arg_8], 0
0x140013b0e  lea     rdx, [rsp+48h+arg_8]
0x140013b13  xor     edi, edi
0x140013b15  call    NfsResMgrpResourceRecordLookupAndReference
0x140013b1a  mov     esi, eax
0x140013b1c  test    eax, eax
0x140013b1e  js      short loc_140013B5B
0x140013b20  mov     rbx, [rsp+48h+arg_8]
0x140013b25  cmp     [rbx+3Ch], edi
0x140013b28  jz      short loc_140013B31
0x140013b2a  mov     esi, 0C000000Dh
0x140013b2f  jmp     short loc_140013B37
0x140013b31  mov     edi, [rbx+0E8h]
0x140013b37  xor     ecx, ecx
0x140013b39  xor     eax, eax
0x140013b3b  lock cmpxchg [rbx+4], ecx
0x140013b40  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140013b47  jz      short loc_140013B57
0x140013b49  lea     r8d, [rcx+1]
0x140013b4d  mov     edx, eax
0x140013b4f  mov     rcx, rbx
0x140013b52  call    NfsReferenceHistoryCaptureRecord
0x140013b57  lock dec dword ptr [rbx+4]
0x140013b5b  xor     eax, eax
0x140013b5d  test    esi, esi
0x140013b5f  cmovs   edi, eax
0x140013b62  mov     eax, esi
0x140013b64  mov     [r14], edi
0x140013b67  add     rsp, 28h
0x140013b6b  pop     r14
0x140013b6d  pop     rdi
0x140013b6e  pop     rsi
0x140013b6f  pop     rbx
0x140013b70  retn
```
