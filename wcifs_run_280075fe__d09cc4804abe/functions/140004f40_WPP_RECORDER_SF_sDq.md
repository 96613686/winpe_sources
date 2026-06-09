# WPP_RECORDER_SF_sDq

- ea: `0x140004f40`
- end: `0x140005048`
- name: `WPP_RECORDER_SF_sDq`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026de0`

## callees

- `0x140004f40`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005028`
- `WppRecorder!WppAutoLogTrace` at `0x140005028`

## string_xrefs

- `0x140004f63`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c

```

## disassembly

```asm
0x140004f40  mov     r11, rsp
0x140004f43  mov     [r11+8], rbx
0x140004f47  mov     [r11+10h], r14
0x140004f4b  push    r15
0x140004f4d  sub     rsp, 70h
0x140004f51  mov     rbx, rcx
0x140004f54  mov     [rsp+78h+var_18], 2BDh
0x140004f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f63  lea     r15, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140004f6a  mov     r14d, 14h
0x140004f70  mov     eax, [rcx+2Ch]
0x140004f73  test    al, 10h
0x140004f75  jz      short loc_140004FCF
0x140004f77  cmp     byte ptr [rcx+29h], 3
0x140004f7b  jb      short loc_140004FCF
0x140004f7d  mov     rax, cs:pfnWppTraceMessage
0x140004f84  lea     rdx, [r11+40h]
0x140004f88  mov     rcx, [rcx+18h]
0x140004f8c  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140004f93  mov     qword ptr [r11-28h], 0
0x140004f9b  mov     r9d, r14d
0x140004f9e  mov     qword ptr [r11-30h], 8
0x140004fa6  mov     [r11-38h], rdx
0x140004faa  lea     rdx, [r11-18h]
0x140004fae  mov     qword ptr [r11-40h], 4
0x140004fb6  mov     [r11-48h], rdx
0x140004fba  lea     edx, [r14+17h]
0x140004fbe  mov     qword ptr [r11-50h], 23h ; '#'
0x140004fc6  mov     [r11-58h], r15
0x140004fca  call    _guard_dispatch_icall
0x140004fcf  mov     [rsp+78h+var_20], 0
0x140004fd8  lea     rax, [rsp+78h+arg_38]
0x140004fe0  mov     [rsp+78h+var_28], 8
0x140004fe9  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140004ff0  mov     [rsp+78h+var_30], rax
0x140004ff5  mov     edx, 3
0x140004ffa  mov     [rsp+78h+var_38], 4
0x140005003  lea     rax, [rsp+78h+var_18]
0x140005008  mov     [rsp+78h+var_40], rax
0x14000500d  mov     rcx, rbx
0x140005010  mov     [rsp+78h+var_48], 23h ; '#'
0x140005019  mov     [rsp+78h+var_50], r15
0x14000501e  lea     r8d, [rdx+2]
0x140005022  mov     [rsp+78h+var_58], r14w
0x140005028  call    cs:__imp_WppAutoLogTrace
0x14000502f  nop     dword ptr [rax+rax+00h]
0x140005034  lea     r11, [rsp+78h+var_8]
0x140005039  mov     rbx, [r11+10h]
0x14000503d  mov     r14, [r11+18h]
0x140005041  mov     rsp, r11
0x140005044  pop     r15
0x140005046  retn
```
