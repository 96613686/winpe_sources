# CRtfIFilter::GetClassID(_GUID *)

- ea: `0x1800131b0`
- end: `0x1800131be`
- name: `?GetClassID@CRtfIFilter@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CRtfIFilter *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800131d0`

## pseudocode

```c
__int64 __fastcall CRtfIFilter::GetClassID(CRtfIFilter *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_RtfIFilter;
  return result;
}

```

## disassembly

```asm
0x1800131b0  movups  xmm0, xmmword ptr cs:?CLSID_RtfIFilter@@3U_GUID@@A.Data1; _GUID CLSID_RtfIFilter ...
0x1800131b7  xor     eax, eax
0x1800131b9  movdqu  xmmword ptr [rdx], xmm0
0x1800131bd  retn
```
