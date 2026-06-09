# SmpConfigureExecute

- ea: `0x1400134e0`
- end: `0x140013531`
- name: `SmpConfigureExecute`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400134e0`
- `0x1400182cc`

## pseudocode

```c
__int64 __fastcall SmpConfigureExecute(__int64 a1, __int64 a2, const WCHAR *a3, __int64 a4, int a5, __int64 a6)
{
  __int64 result; // rax
  struct _UNICODE_STRING *v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  result = SmpSaveRegistryValue((struct _UNICODE_STRING **)(a6 + 40), a3, 0, 1, &v7);
  if ( (int)result >= 0 )
  {
    ++*(_DWORD *)a6;
    *(_DWORD *)(a6 + 4) += v7[1].Length + 2;
  }
  return result;
}

```

## disassembly

```asm
0x1400134e0  push    rbx
0x1400134e2  sub     rsp, 40h
0x1400134e6  mov     rbx, [rsp+48h+arg_28]
0x1400134eb  lea     rdx, [rsp+48h+var_18]
0x1400134f0  mov     rax, r8
0x1400134f3  mov     [rsp+48h+var_28], rdx
0x1400134f8  mov     r9d, 1
0x1400134fe  mov     [rsp+48h+var_18], 0
0x140013507  xor     r8d, r8d
0x14001350a  mov     rdx, rax
0x14001350d  lea     rcx, [rbx+28h]
0x140013511  call    SmpSaveRegistryValue
0x140013516  test    eax, eax
0x140013518  js      short loc_14001352B
0x14001351a  inc     dword ptr [rbx]
0x14001351c  mov     rcx, [rsp+48h+var_18]
0x140013521  movzx   edx, word ptr [rcx+10h]
0x140013525  add     edx, 2
0x140013528  add     [rbx+4], edx
0x14001352b  add     rsp, 40h
0x14001352f  pop     rbx
0x140013530  retn
```
