# HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(void)

- ea: `0x180002008`
- end: `0x18000208e`
- name: `??0HTTP_LOG_FILE_CONFIG_CONTEXT@@QEAA@XZ`
- size: `134`
- prototype: `HTTP_LOG_FILE_CONFIG_CONTEXT *__fastcall(HTTP_LOG_FILE_CONFIG_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180005ccc`
- `0x180007338`
- `0x1800073e8`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180002047`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002052`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002047`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002052`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002060`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002060`

## pseudocode

```c
HTTP_LOG_FILE_CONFIG_CONTEXT *__fastcall HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(
        HTTP_LOG_FILE_CONFIG_CONTEXT *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 1;
  STRU::STRU((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)this + 48));
  STRU::STRU((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)this + 104));
  MULTISZ::MULTISZ((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)this + 160));
  *((_DWORD *)this + 54) = 4096;
  *(_QWORD *)((char *)this + 220) = 0x10000;
  *((_DWORD *)this + 57) &= 0xFFFFC000;
  return this;
}

```

## disassembly

```asm
0x180002008  mov     [rsp+arg_0], rcx
0x18000200d  push    rbx
0x18000200e  sub     rsp, 20h
0x180002012  mov     rbx, rcx
0x180002015  mov     qword ptr [rcx], 0
0x18000201c  mov     qword ptr [rcx+8], 0
0x180002024  mov     qword ptr [rcx+10h], 0
0x18000202c  mov     qword ptr [rcx+18h], 0
0x180002034  mov     qword ptr [rcx+20h], 0
0x18000203c  mov     dword ptr [rcx+28h], 1
0x180002043  add     rcx, 30h ; '0'
0x180002047  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000204d  nop
0x18000204e  lea     rcx, [rbx+68h]
0x180002052  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002058  nop
0x180002059  lea     rcx, [rbx+0A0h]
0x180002060  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002066  mov     dword ptr [rbx+0D8h], 1000h
0x180002070  mov     qword ptr [rbx+0DCh], 10000h
0x18000207b  and     dword ptr [rbx+0E4h], 0FFFFC000h
0x180002085  mov     rax, rbx
0x180002088  add     rsp, 20h
0x18000208c  pop     rbx
0x18000208d  retn
```
