# LOG_SVC_CONFIG_PATH_MAPPER::MapPath(ushort *,ushort *,ushort * *)

- ea: `0x18000c7f0`
- end: `0x18000c855`
- name: `?MapPath@LOG_SVC_CONFIG_PATH_MAPPER@@UEAAJPEAG0PEAPEAG@Z`
- size: `101`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_PATH_MAPPER *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c7f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c814`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c830`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c814`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c830`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_PATH_MAPPER::MapPath(
        LOG_SVC_CONFIG_PATH_MAPPER *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v4; // rax
  unsigned __int16 *v6; // rcx
  __int64 result; // rax

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( (unsigned int)v4 > 0x18 )
  {
    v6 = SysAllocString(&LocaleName);
    if ( !v6 )
      return 2147942414LL;
  }
  else
  {
    v6 = SysAllocString(a3);
    if ( !v6 )
      return 2147942408LL;
  }
  result = 0;
  *a4 = v6;
  return result;
}

```

## disassembly

```asm
0x18000c7f0  mov     [rsp+arg_0], rbx
0x18000c7f5  push    rdi
0x18000c7f6  sub     rsp, 20h
0x18000c7fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c7fe  mov     rbx, r9
0x18000c801  xor     edi, edi
0x18000c803  inc     rax
0x18000c806  cmp     [rdx+rax*2], di
0x18000c80a  jnz     short loc_18000C803
0x18000c80c  cmp     eax, 18h
0x18000c80f  ja      short loc_18000C829
0x18000c811  mov     rcx, r8; psz
0x18000c814  call    cs:__imp_SysAllocString
0x18000c81a  mov     rcx, rax
0x18000c81d  test    rax, rax
0x18000c820  jnz     short loc_18000C845
0x18000c822  mov     eax, 80070008h
0x18000c827  jmp     short loc_18000C84A
0x18000c829  lea     rcx, LocaleName; psz
0x18000c830  call    cs:__imp_SysAllocString
0x18000c836  mov     rcx, rax
0x18000c839  test    rax, rax
0x18000c83c  jnz     short loc_18000C845
0x18000c83e  mov     eax, 8007000Eh
0x18000c843  jmp     short loc_18000C84A
0x18000c845  mov     eax, edi
0x18000c847  mov     [rbx], rcx
0x18000c84a  mov     rbx, [rsp+28h+arg_0]
0x18000c84f  add     rsp, 20h
0x18000c853  pop     rdi
0x18000c854  retn
```
