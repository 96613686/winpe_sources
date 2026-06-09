# _bstr_t::_Free(void)

- ea: `0x180003fec`
- end: `0x180004058`
- name: `?_Free@_bstr_t@@AEAAXXZ`
- size: `108`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `35`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003c88`
- `0x180003cb8`
- `0x180003cc4`
- `0x180004094`
- `0x180005a38`
- `0x180005a48`
- `0x180005b1c`
- `0x180005c5c`
- `0x180005d58`
- `0x180005e94`
- `0x180006c28`
- `0x180006d2c`
- `0x180006f18`
- `0x1800072b4`
- `0x180007754`
- `0x180007afc`
- `0x180007b44`
- `0x180008010`
- `0x180008610`
- `0x180008730`
- `0x180008c74`
- `0x180009260`
- `0x180009520`
- `0x180009630`
- `0x180009c50`
- `0x180009d50`
- `0x18000a698`
- `0x18000a838`
- `0x18000ab84`
- `0x18000b5c8`
- `0x18000b78c`
- `0x18000bcf4`
- `0x18000bfa0`
- `0x18000c01c`
- `0x18000c4d0`

## callees

- `0x180002434`
- `0x180003fec`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004016`
- `OLEAUT32!__imp_SysFreeString` at `0x180004016`

## pseudocode

```c
void __fastcall _bstr_t::_Free(_bstr_t *this)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v1 )
      {
        SysFreeString(*(BSTR *)v1);
        *(_QWORD *)v1 = 0;
      }
      v3 = *(void **)(v1 + 8);
      if ( v3 )
      {
        operator delete(v3);
        *(_QWORD *)(v1 + 8) = 0;
      }
      operator delete((void *)v1);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180003fec  mov     [rsp+arg_8], rbx
0x180003ff1  push    rdi
0x180003ff2  sub     rsp, 20h
0x180003ff6  mov     rbx, [rcx]
0x180003ff9  mov     rdi, rcx
0x180003ffc  test    rbx, rbx
0x180003fff  jz      short loc_18000404D
0x180004001  or      eax, 0FFFFFFFFh
0x180004004  lock xadd [rbx+10h], eax
0x180004009  cmp     eax, 1
0x18000400c  jnz     short loc_180004046
0x18000400e  mov     rcx, [rbx]; bstrString
0x180004011  test    rcx, rcx
0x180004014  jz      short loc_180004023
0x180004016  call    cs:__imp_SysFreeString
0x18000401c  mov     qword ptr [rbx], 0
0x180004023  mov     rcx, [rbx+8]; Block
0x180004027  test    rcx, rcx
0x18000402a  jz      short loc_180004039
0x18000402c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004031  mov     qword ptr [rbx+8], 0
0x180004039  mov     edx, 18h
0x18000403e  mov     rcx, rbx; Block
0x180004041  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004046  mov     qword ptr [rdi], 0
0x18000404d  mov     rbx, [rsp+28h+arg_8]
0x180004052  add     rsp, 20h
0x180004056  pop     rdi
0x180004057  retn
```
