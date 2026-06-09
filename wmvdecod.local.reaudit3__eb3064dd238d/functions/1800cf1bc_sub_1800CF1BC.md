# sub_1800CF1BC

- ea: `0x1800cf1bc`
- end: `0x1800cf21a`
- name: `sub_1800CF1BC`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007c210`

## callees

- `0x1800cec70`
- `0x1800cf1bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cf1d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cf1d2`

## pseudocode

```c
void sub_1800CF1BC()
{
  char *v0; // rbx
  char *v1; // rcx

  if ( dword_180290B98 )
  {
    DeleteCriticalSection(&stru_1802844F0);
    dword_180290B98 = 0;
  }
  v0 = (char *)lpAddress;
  while ( v0 )
  {
    v1 = v0;
    v0 = (char *)*((_QWORD *)v0 + 8058);
    sub_1800CEC70(v1);
    --qword_1802844D0;
  }
  lpAddress = 0;
}

```

## disassembly

```asm
0x1800cf1bc  push    rbx
0x1800cf1be  sub     rsp, 20h
0x1800cf1c2  cmp     cs:dword_180290B98, 0
0x1800cf1c9  jz      short loc_1800CF1E8
0x1800cf1cb  lea     rcx, stru_1802844F0; lpCriticalSection
0x1800cf1d2  call    cs:DeleteCriticalSection
0x1800cf1d9  nop     dword ptr [rax+rax+00h]
0x1800cf1de  mov     cs:dword_180290B98, 0
0x1800cf1e8  mov     rbx, cs:lpAddress
0x1800cf1ef  jmp     short loc_1800CF207
0x1800cf1f1  mov     rcx, rbx; lpAddress
0x1800cf1f4  mov     rbx, [rbx+0FBD0h]
0x1800cf1fb  call    sub_1800CEC70
0x1800cf200  dec     cs:qword_1802844D0
0x1800cf207  test    rbx, rbx
0x1800cf20a  jnz     short loc_1800CF1F1
0x1800cf20c  mov     cs:lpAddress, rbx
0x1800cf213  add     rsp, 20h
0x1800cf217  pop     rbx
0x1800cf218  retn
```
