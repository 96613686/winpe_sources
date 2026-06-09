# ATL::CComObject<CWMPRichPreviewRemoteService>::Release(void)

- ea: `0x140007b20`
- end: `0x140007b77`
- name: `?Release@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ`
- size: `87`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140007b80`
- `0x140007b90`

## callees

- `0x140001008`
- `0x140002190`
- `0x140007b20`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[6];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[6] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      if ( a1 )
      {
        ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>((__int64)a1);
        operator delete(a1);
      }
      CExeModule::Unlock((CExeModule *)a1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140007b20  mov     [rsp+arg_0], rbx
0x140007b25  push    rdi
0x140007b26  sub     rsp, 20h
0x140007b2a  mov     edi, [rcx+18h]
0x140007b2d  mov     rbx, rcx
0x140007b30  cmp     edi, 7FFFFFFFh
0x140007b36  jnz     short loc_140007B3F
0x140007b38  mov     edi, 7FFFFFFEh
0x140007b3d  jmp     short loc_140007B6A
0x140007b3f  sub     edi, 1
0x140007b42  mov     [rcx+18h], edi
0x140007b45  jnz     short loc_140007B6A
0x140007b47  lock inc cs:dword_1400153D8
0x140007b4e  test    rbx, rbx
0x140007b51  jz      short loc_140007B65
0x140007b53  call    ??1?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@QEAA@XZ; ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>(void)
0x140007b58  mov     edx, 48h ; 'H'; unsigned __int64
0x140007b5d  mov     rcx, rbx; void *
0x140007b60  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007b65  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007b6a  mov     rbx, [rsp+28h+arg_0]
0x140007b6f  mov     eax, edi
0x140007b71  add     rsp, 20h
0x140007b75  pop     rdi
0x140007b76  retn
```
