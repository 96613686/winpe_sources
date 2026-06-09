# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400080e8`
- end: `0x14000813e`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `36`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f34`
- `0x140007fec`
- `0x14000805c`
- `0x140008820`
- `0x140012998`
- `0x140013ebc`
- `0x140014948`
- `0x14001498c`
- `0x140014a00`
- `0x140015ac0`
- `0x140015b78`
- `0x140015c14`
- `0x140015c80`
- `0x140018914`
- `0x140019afc`
- `0x140019b78`
- `0x140019c3c`
- `0x14001a824`
- `0x14001a884`
- `0x14001a8f4`
- `0x14001a960`
- `0x14001a9e0`
- `0x14001b560`
- `0x14001bcb0`
- `0x14001bd74`
- `0x14001be88`
- `0x14001e918`
- `0x1400218a4`
- `0x140021930`
- `0x140021b08`
- `0x140022db0`
- `0x140024100`
- `0x1400241ac`
- `0x140024438`
- `0x1400244d8`
- `0x140024564`

## callees

- `0x1400080e8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000811e`
- `ntoskrnl!EtwWriteTransfer` at `0x14000811e`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_140036058;
  if ( qword_140036058 )
  {
    UserData->Ptr = qword_140036058;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(PROV_SRV2_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400080e8  sub     rsp, 38h
0x1400080ec  mov     rcx, cs:qword_140036058
0x1400080f3  mov     rax, [rsp+38h+arg_20]
0x1400080f8  test    rcx, rcx
0x1400080fb  jnz     short loc_140008130
0x1400080fd  mov     [rax], rcx
0x140008100  xor     r10d, r10d
0x140008103  mov     [rax+8], ecx
0x140008106  mov     [rsp+38h+UserData], rax; UserData
0x14000810b  mov     [rax+0Ch], r10d
0x14000810f  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140008116  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000811b  xor     r9d, r9d; RelatedActivityId
0x14000811e  call    cs:__imp_EtwWriteTransfer
0x140008125  nop     dword ptr [rax+rax+00h]
0x14000812a  add     rsp, 38h
0x14000812e  retn
0x140008130  mov     [rax], rcx
0x140008133  mov     r10d, 2
0x140008139  movzx   ecx, word ptr [rcx]
0x14000813c  jmp     short loc_140008103
```
