# EnterMgmAPI

- ea: `0x180014f98`
- end: `0x180014fd8`
- name: `EnterMgmAPI`
- size: `64`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x180012620`
- `0x180012800`
- `0x180012d80`
- `0x180012ed0`
- `0x180013020`
- `0x180013140`
- `0x180013260`
- `0x180013390`
- `0x1800134c0`
- `0x1800136d0`
- `0x1800137e0`
- `0x180013930`
- `0x180014200`
- `0x180014580`
- `0x180014970`
- `0x180016470`
- `0x180018070`
- `0x180018c10`
- `0x180019de0`
- `0x18001a360`

## callees

- `0x180014f98`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014fa5`
- `KERNEL32!EnterCriticalSection` at `0x180014fa5`
- `KERNEL32!LeaveCriticalSection` at `0x180014fca`
- `KERNEL32!LeaveCriticalSection` at `0x180014fca`

## pseudocode

```c
__int64 EnterMgmAPI()
{
  unsigned int v0; // ebx

  EnterCriticalSection(&ig);
  if ( dword_18002B908 == 101 )
  {
    v0 = 1;
    ++dword_18002B918;
  }
  else
  {
    v0 = 0;
  }
  LeaveCriticalSection(&ig);
  return v0;
}

```

## disassembly

```asm
0x180014f98  push    rbx
0x180014f9a  sub     rsp, 20h
0x180014f9e  lea     rcx, ig; lpCriticalSection
0x180014fa5  call    cs:__imp_EnterCriticalSection
0x180014fab  cmp     cs:dword_18002B908, 65h ; 'e'
0x180014fb2  jnz     short loc_180014FC1
0x180014fb4  mov     ebx, 1
0x180014fb9  add     cs:dword_18002B918, ebx
0x180014fbf  jmp     short loc_180014FC3
0x180014fc1  xor     ebx, ebx
0x180014fc3  lea     rcx, ig; lpCriticalSection
0x180014fca  call    cs:__imp_LeaveCriticalSection
0x180014fd0  mov     eax, ebx
0x180014fd2  add     rsp, 20h
0x180014fd6  pop     rbx
0x180014fd7  retn
```
