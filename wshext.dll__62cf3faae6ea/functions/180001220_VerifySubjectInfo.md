# VerifySubjectInfo

- ea: `0x180001220`
- end: `0x18000125e`
- name: `VerifySubjectInfo`
- size: `62`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x1800093c0`
- `0x180009a90`
- `0x180009be0`

## callees

- `0x180001220`
- `0x180001940`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001254`
- `KERNEL32!SetLastError` at `0x180001254`

## pseudocode

```c
__int64 __fastcall VerifySubjectInfo(__int64 a1)
{
  DWORD v2; // ecx

  if ( a1 && *(_DWORD *)a1 == 128 )
  {
    if ( (unsigned int)ClassifyGuid(*(_QWORD **)(a1 + 8)) )
      return 1;
    v2 = -2146762749;
  }
  else
  {
    v2 = 87;
  }
  SetLastError(v2);
  return 0;
}

```

## disassembly

```asm
0x180001220  sub     rsp, 28h
0x180001224  test    rcx, rcx
0x180001227  jz      short loc_180001248
0x180001229  cmp     dword ptr [rcx], 80h
0x18000122f  jnz     short loc_180001248
0x180001231  mov     rcx, [rcx+8]
0x180001235  call    ClassifyGuid
0x18000123a  test    eax, eax
0x18000123c  jz      short loc_18000124F
0x18000123e  mov     eax, 1
0x180001243  add     rsp, 28h
0x180001247  retn
0x180001248  mov     ecx, 57h ; 'W'
0x18000124d  jmp     short loc_180001254
0x18000124f  mov     ecx, 800B0003h; dwErrCode
0x180001254  call    cs:__imp_SetLastError
0x18000125a  xor     eax, eax
0x18000125c  jmp     short loc_180001243
```
