# WcExpansionCsqCompleteCanceledIo

- ea: `0x1400183d0`
- end: `0x140018418`
- name: `WcExpansionCsqCompleteCanceledIo`
- size: `72`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400183d0`

## import_xrefs

- `FLTMGR!FltCompletePendedPostOperation` at `0x1400183e2`
- `FLTMGR!FltCompletePendedPostOperation` at `0x1400183e2`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140018406`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140018406`

## pseudocode

```c
void __fastcall WcExpansionCsqCompleteCanceledIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  if ( (Cbd->Flags & 0x80000) != 0 )
  {
    FltCompletePendedPostOperation(Cbd);
  }
  else
  {
    Cbd->IoStatus.Status = -1073741536;
    Cbd->IoStatus.Information = 0;
    FltCompletePendedPreOperation(Cbd, FLT_PREOP_COMPLETE, 0);
  }
}

```

## disassembly

```asm
0x1400183d0  sub     rsp, 28h
0x1400183d4  test    dword ptr [rdx], 80000h
0x1400183da  mov     r9, rdx
0x1400183dd  mov     rcx, rdx; CallbackData
0x1400183e0  jz      short loc_1400183F0
0x1400183e2  call    cs:__imp_FltCompletePendedPostOperation
0x1400183e9  nop     dword ptr [rax+rax+00h]
0x1400183ee  jmp     short loc_140018412
0x1400183f0  xor     r8d, r8d; Context
0x1400183f3  mov     dword ptr [rdx+18h], 0C0000120h
0x1400183fa  mov     qword ptr [rdx+20h], 0
0x140018402  lea     edx, [r8+4]; CallbackStatus
0x140018406  call    cs:__imp_FltCompletePendedPreOperation
0x14001840d  nop     dword ptr [rax+rax+00h]
0x140018412  add     rsp, 28h
0x140018416  retn
```
