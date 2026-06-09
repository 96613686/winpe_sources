# CSFPIntegrityCheckAndRepair::GetSMISchemaHivePath(ushort const *,ushort * *)

- ea: `0x180005200`
- end: `0x180005252`
- name: `?GetSMISchemaHivePath@CSFPIntegrityCheckAndRepair@@EEAAJPEBGPEAPEAG@Z`
- size: `82`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001de0`
- `0x180005200`
- `0x180010448`

## string_xrefs

- `0x180005216`: `system32\smi\store\Machine\`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::GetSMISchemaHivePath(
        CSFPIntegrityCheckAndRepair *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v4; // eax
  unsigned __int16 *v5; // rcx
  unsigned int v6; // ebx
  unsigned __int16 *v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v4 = SczAllocConcat2Sz(&v8, a2, L"system32\\smi\\store\\Machine\\");
  v5 = v8;
  v6 = v4;
  if ( v4 >= 0 )
  {
    *a3 = v8;
    v5 = 0;
  }
  if ( v5 )
    operator delete(v5 - 4);
  return v6;
}

```

## disassembly

```asm
0x180005200  mov     [rsp+arg_0], rbx
0x180005205  push    rdi
0x180005206  sub     rsp, 20h
0x18000520a  mov     rdi, r8
0x18000520d  mov     [rsp+28h+arg_18], 0
0x180005216  lea     r8, aSystem32SmiSto; "system32\\smi\\store\\Machine\\"
0x18000521d  lea     rcx, [rsp+28h+arg_18]
0x180005222  call    SczAllocConcat2Sz
0x180005227  mov     rcx, [rsp+28h+arg_18]
0x18000522c  mov     ebx, eax
0x18000522e  test    eax, eax
0x180005230  js      short loc_180005237
0x180005232  mov     [rdi], rcx
0x180005235  xor     ecx, ecx
0x180005237  test    rcx, rcx
0x18000523a  jz      short loc_180005245
0x18000523c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180005240  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005245  mov     eax, ebx
0x180005247  mov     rbx, [rsp+28h+arg_0]
0x18000524c  add     rsp, 20h
0x180005250  pop     rdi
0x180005251  retn
```
