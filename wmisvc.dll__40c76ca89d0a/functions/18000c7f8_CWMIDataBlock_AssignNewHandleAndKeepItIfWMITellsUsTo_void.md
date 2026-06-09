# CWMIDataBlock::AssignNewHandleAndKeepItIfWMITellsUsTo(void)

- ea: `0x18000c7f8`
- end: `0x18000c8a2`
- name: `?AssignNewHandleAndKeepItIfWMITellsUsTo@CWMIDataBlock@@IEAAHXZ`
- size: `170`
- prototype: `__int64 __fastcall(CWMIDataBlock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000abc0`

## callees

- `0x18000c7f8`
- `0x180019a1c`

## import_xrefs

- `WMICLNT!WmiQueryGuidInformation` at `0x18000c848`
- `WMICLNT!WmiQueryGuidInformation` at `0x18000c848`
- `WMICLNT!WmiOpenBlock` at `0x18000c81f`
- `WMICLNT!WmiOpenBlock` at `0x18000c81f`

## pseudocode

```c
__int64 __fastcall CWMIDataBlock::AssignNewHandleAndKeepItIfWMITellsUsTo(CWMIDataBlock *this)
{
  void **v2; // rsi
  unsigned int v3; // edi
  __int64 *v4; // rdx
  __int64 v5; // rax
  struct _GUID v7; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  try
  {
    v2 = (void **)((char *)this + 24);
    v3 = WmiOpenBlock(*((_QWORD *)this + 2) + 56LL, *((unsigned int *)this + 293), (char *)this + 24);
    if ( !v3 )
    {
      v8 = 8;
      if ( !(unsigned int)WmiQueryGuidInformation(*v2, &v8) && BYTE4(v8) && *((_DWORD *)this + 2) )
      {
        *((_DWORD *)this + 8) = 0;
        v4 = (__int64 *)*((_QWORD *)this + 2);
        v5 = *v4;
        v7 = *(struct _GUID *)(v4 + 7);
        CHandleMap::Add(*(CHandleMap **)(v5 + 32), &v7, *v2, *((_DWORD *)this + 293));
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)-2147418113;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c7f8  mov     [rsp+arg_0], rbx
0x18000c7fd  mov     [rsp+arg_10], rsi
0x18000c802  push    rdi
0x18000c803  sub     rsp, 40h
0x18000c807  mov     rbx, rcx
0x18000c80a  lea     rsi, [rcx+18h]
0x18000c80e  mov     rcx, [rcx+10h]
0x18000c812  add     rcx, 38h ; '8'
0x18000c816  mov     r8, rsi
0x18000c819  mov     edx, [rbx+494h]
0x18000c81f  call    cs:__imp_WmiOpenBlock
0x18000c825  mov     edi, eax
0x18000c827  mov     [rsp+48h+var_28], eax
0x18000c82b  test    eax, eax
0x18000c82d  jnz     short loc_18000C88A
0x18000c82f  mov     [rsp+48h+arg_8], 0
0x18000c838  mov     dword ptr [rsp+48h+arg_8], 8
0x18000c840  lea     rdx, [rsp+48h+arg_8]
0x18000c845  mov     rcx, [rsi]
0x18000c848  call    cs:__imp_WmiQueryGuidInformation
0x18000c84e  test    eax, eax
0x18000c850  jnz     short loc_18000C88A
0x18000c852  cmp     byte ptr [rsp+48h+arg_8+4], al
0x18000c856  jz      short loc_18000C88A
0x18000c858  cmp     [rbx+8], eax
0x18000c85b  jz      short loc_18000C88A
0x18000c85d  mov     [rbx+20h], eax
0x18000c860  mov     rdx, [rbx+10h]
0x18000c864  mov     rax, [rdx]
0x18000c867  movups  xmm0, xmmword ptr [rdx+38h]
0x18000c86b  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18000c871  mov     r9d, [rbx+494h]; unsigned int
0x18000c878  mov     r8, [rsi]; void *
0x18000c87b  lea     rdx, [rsp+48h+var_18]; struct _GUID
0x18000c880  mov     rcx, [rax+20h]; this
0x18000c884  call    ?Add@CHandleMap@@QEAAJU_GUID@@PEAXK@Z; CHandleMap::Add(_GUID,void *,ulong)
0x18000c889  nop
0x18000c88a  jmp     short loc_18000C890
0x18000c88c  mov     edi, [rsp+48h+var_28]
0x18000c890  mov     eax, edi
0x18000c892  mov     rbx, [rsp+48h+arg_0]
0x18000c897  mov     rsi, [rsp+48h+arg_10]
0x18000c89c  add     rsp, 40h
0x18000c8a0  pop     rdi
0x18000c8a1  retn
```
