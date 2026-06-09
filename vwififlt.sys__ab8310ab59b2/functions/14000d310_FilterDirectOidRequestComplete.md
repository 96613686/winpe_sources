# FilterDirectOidRequestComplete

- ea: `0x14000d310`
- end: `0x14000d397`
- name: `FilterDirectOidRequestComplete`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009bec`
- `0x14000d310`
- `0x14000d8ec`
- `0x14000d91c`

## pseudocode

```c
void __fastcall FilterDirectOidRequestComplete(__int64 a1, __int64 a2, unsigned int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 206, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  FilterDirectOidRequestCompleteCommon(a1, a2, a3, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x14000d310  push    rbx
0x14000d312  push    rbp
0x14000d313  push    rsi
0x14000d314  push    rdi
0x14000d315  sub     rsp, 28h
0x14000d319  mov     ebx, r8d
0x14000d31c  mov     rdi, rdx
0x14000d31f  mov     rsi, rcx
0x14000d322  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d329  lea     rbp, WPP_GLOBAL_Control
0x14000d330  cmp     rcx, rbp
0x14000d333  jz      short loc_14000D351
0x14000d335  mov     eax, [rcx+2Ch]
0x14000d338  test    al, 20h
0x14000d33a  jz      short loc_14000D351
0x14000d33c  mov     rcx, [rcx+18h]
0x14000d340  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000d347  mov     edx, 0CEh
0x14000d34c  call    WPP_SF_
0x14000d351  mov     r9b, 1
0x14000d354  mov     r8d, ebx
0x14000d357  mov     rdx, rdi
0x14000d35a  mov     rcx, rsi
0x14000d35d  call    FilterDirectOidRequestCompleteCommon
0x14000d362  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d369  cmp     rcx, rbp
0x14000d36c  jz      short loc_14000D38D
0x14000d36e  mov     eax, [rcx+2Ch]
0x14000d371  test    al, 20h
0x14000d373  jz      short loc_14000D38D
0x14000d375  mov     rcx, [rcx+18h]
0x14000d379  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000d380  mov     edx, 0CFh
0x14000d385  xor     r9d, r9d
0x14000d388  call    WPP_SF_d
0x14000d38d  add     rsp, 28h
0x14000d391  pop     rdi
0x14000d392  pop     rsi
0x14000d393  pop     rbp
0x14000d394  pop     rbx
0x14000d395  retn
```
