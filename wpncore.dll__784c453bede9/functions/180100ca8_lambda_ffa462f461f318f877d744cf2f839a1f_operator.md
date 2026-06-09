# _lambda_ffa462f461f318f877d744cf2f839a1f_::operator()

- ea: `0x180100ca8`
- end: `0x180100d64`
- name: `_lambda_ffa462f461f318f877d744cf2f839a1f_::operator()`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180100634`

## callees

- `0x180100ca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100d4a`

## pseudocode

```c
void ***__fastcall lambda_ffa462f461f318f877d744cf2f839a1f_::operator()(void ****a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void ***result; // rax
  void *v7; // rcx

  v2 = (**a1)[5];
  if ( v2 )
  {
    CoTaskMemFree(v2);
    (**a1)[5] = 0;
  }
  v3 = ***a1;
  if ( v3 )
  {
    CoTaskMemFree(v3);
    ***a1 = 0;
  }
  v4 = (**a1)[1];
  if ( v4 )
  {
    CoTaskMemFree(v4);
    (**a1)[1] = 0;
  }
  v5 = (**a1)[10];
  if ( v5 )
  {
    CoTaskMemFree(v5);
    (**a1)[10] = 0;
  }
  result = *a1;
  v7 = (**a1)[11];
  if ( v7 )
  {
    CoTaskMemFree(v7);
    result = *a1;
    (**a1)[11] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180100ca8  push    rbx
0x180100caa  sub     rsp, 20h
0x180100cae  mov     rax, [rcx]
0x180100cb1  mov     rbx, rcx
0x180100cb4  mov     rdx, [rax]
0x180100cb7  mov     rcx, [rdx+28h]; pv
0x180100cbb  test    rcx, rcx
0x180100cbe  jz      short loc_180100CD4
0x180100cc0  call    cs:__imp_CoTaskMemFree
0x180100cc6  mov     rax, [rbx]
0x180100cc9  mov     rdx, [rax]
0x180100ccc  mov     qword ptr [rdx+28h], 0
0x180100cd4  mov     rax, [rbx]
0x180100cd7  mov     rcx, [rax]
0x180100cda  mov     rcx, [rcx]; pv
0x180100cdd  test    rcx, rcx
0x180100ce0  jz      short loc_180100CF5
0x180100ce2  call    cs:__imp_CoTaskMemFree
0x180100ce8  mov     rax, [rbx]
0x180100ceb  mov     rcx, [rax]
0x180100cee  mov     qword ptr [rcx], 0
0x180100cf5  mov     rax, [rbx]
0x180100cf8  mov     rcx, [rax]
0x180100cfb  mov     rcx, [rcx+8]; pv
0x180100cff  test    rcx, rcx
0x180100d02  jz      short loc_180100D18
0x180100d04  call    cs:__imp_CoTaskMemFree
0x180100d0a  mov     rax, [rbx]
0x180100d0d  mov     rcx, [rax]
0x180100d10  mov     qword ptr [rcx+8], 0
0x180100d18  mov     rax, [rbx]
0x180100d1b  mov     rcx, [rax]
0x180100d1e  mov     rcx, [rcx+50h]; pv
0x180100d22  test    rcx, rcx
0x180100d25  jz      short loc_180100D3B
0x180100d27  call    cs:__imp_CoTaskMemFree
0x180100d2d  mov     rax, [rbx]
0x180100d30  mov     rcx, [rax]
0x180100d33  mov     qword ptr [rcx+50h], 0
0x180100d3b  mov     rax, [rbx]
0x180100d3e  mov     rcx, [rax]
0x180100d41  mov     rcx, [rcx+58h]; pv
0x180100d45  test    rcx, rcx
0x180100d48  jz      short loc_180100D5E
0x180100d4a  call    cs:__imp_CoTaskMemFree
0x180100d50  mov     rax, [rbx]
0x180100d53  mov     rcx, [rax]
0x180100d56  mov     qword ptr [rcx+58h], 0
0x180100d5e  add     rsp, 20h
0x180100d62  pop     rbx
0x180100d63  retn
```
