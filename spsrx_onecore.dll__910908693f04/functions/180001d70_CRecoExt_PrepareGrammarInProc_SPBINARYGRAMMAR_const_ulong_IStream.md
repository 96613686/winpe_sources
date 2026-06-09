# CRecoExt::PrepareGrammarInProc(SPBINARYGRAMMAR const *,ulong,IStream *)

- ea: `0x180001d70`
- end: `0x180001e33`
- name: `?PrepareGrammarInProc@CRecoExt@@UEAAJPEBUSPBINARYGRAMMAR@@KPEAUIStream@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(CRecoExt *this, const struct SPBINARYGRAMMAR *, int, struct IStream *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001d70`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e0a`

## pseudocode

```c
__int64 __fastcall CRecoExt::PrepareGrammarInProc(
        CRecoExt *this,
        const struct SPBINARYGRAMMAR *a2,
        int a3,
        struct IStream *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rax
  void *v9; // rbx
  unsigned int v10; // edi

  if ( !a2 || !a4 || !a3 )
    return 2147942487LL;
  if ( a2->ulTotalSerializedSize != a3 )
    return 2147766275LL;
  result = 0;
  if ( *((_QWORD *)this + 9) )
  {
    v8 = CoTaskMemAlloc(0x18u);
    v9 = v8;
    if ( v8 )
    {
      *v8 = 47;
      v8[1] = a2;
      v8[2] = a4;
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
              *((_QWORD *)this + 9),
              v8,
              24,
              0,
              0);
      CoTaskMemFree(v9);
      return v10;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001d70  mov     [rsp+arg_10], rbp
0x180001d75  mov     [rsp+arg_18], rsi
0x180001d7a  push    rdi
0x180001d7b  sub     rsp, 30h
0x180001d7f  mov     rsi, r9
0x180001d82  mov     rdi, rdx
0x180001d85  mov     rbp, rcx
0x180001d88  test    rdx, rdx
0x180001d8b  jz      loc_180003732
0x180001d91  test    r9, r9
0x180001d94  jz      loc_180003732
0x180001d9a  test    r8d, r8d
0x180001d9d  jz      loc_180003732
0x180001da3  cmp     [rdx], r8d
0x180001da6  jnz     loc_180003728
0x180001dac  mov     [rsp+38h+arg_8], r14
0x180001db1  xor     r14d, r14d
0x180001db4  mov     eax, r14d
0x180001db7  cmp     [rcx+48h], rax
0x180001dbb  jz      short loc_180001E17
0x180001dbd  mov     ecx, 18h; cb
0x180001dc2  mov     [rsp+38h+arg_0], rbx
0x180001dc7  call    cs:__imp_CoTaskMemAlloc
0x180001dcd  mov     rbx, rax
0x180001dd0  test    rax, rax
0x180001dd3  jz      short loc_180001E2C
0x180001dd5  mov     qword ptr [rax], 2Fh ; '/'
0x180001ddc  xor     r9d, r9d
0x180001ddf  mov     [rax+8], rdi
0x180001de3  mov     r8d, 18h
0x180001de9  mov     [rax+10h], rsi
0x180001ded  mov     rdx, rbx
0x180001df0  mov     rcx, [rbp+48h]
0x180001df4  mov     [rsp+38h+var_18], r14
0x180001df9  mov     rax, [rcx]
0x180001dfc  mov     rax, [rax+20h]
0x180001e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e05  mov     edi, eax
0x180001e07  mov     rcx, rbx; pv
0x180001e0a  call    cs:__imp_CoTaskMemFree
0x180001e10  mov     eax, edi
0x180001e12  mov     rbx, [rsp+38h+arg_0]
0x180001e17  mov     r14, [rsp+38h+arg_8]
0x180001e1c  mov     rbp, [rsp+38h+arg_10]
0x180001e21  mov     rsi, [rsp+38h+arg_18]
0x180001e26  add     rsp, 30h
0x180001e2a  pop     rdi
0x180001e2b  retn
0x180001e2c  mov     eax, 8007000Eh
0x180001e31  jmp     short loc_180001E12
0x180003728  mov     eax, 80045003h
0x18000372d  jmp     loc_180001E1C
0x180003732  mov     eax, 80070057h
0x180003737  jmp     loc_180001E1C
```
