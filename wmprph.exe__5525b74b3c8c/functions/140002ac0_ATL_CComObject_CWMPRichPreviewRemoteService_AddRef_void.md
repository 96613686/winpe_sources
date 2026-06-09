# ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(void)

- ea: `0x140002ac0`
- end: `0x140002ad3`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002ae0`
- `0x140002af0`

## callees

- `0x140002ac0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 24);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140002ac0  mov     edx, [rcx+18h]
0x140002ac3  mov     eax, 7FFFFFFFh
0x140002ac8  cmp     edx, eax
0x140002aca  jz      short locret_140002AD2
0x140002acc  lea     eax, [rdx+1]
0x140002acf  mov     [rcx+18h], eax
0x140002ad2  retn
```
