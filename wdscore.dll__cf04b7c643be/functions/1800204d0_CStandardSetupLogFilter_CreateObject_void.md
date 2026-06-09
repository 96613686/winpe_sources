# CStandardSetupLogFilter::CreateObject(void)

- ea: `0x1800204d0`
- end: `0x18002050e`
- name: `?CreateObject@CStandardSetupLogFilter@@SAPEAVILogProvider@@XZ`
- size: `62`
- prototype: `struct ILogProvider *(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180001144`
- `0x1800204d0`

## pseudocode

```c
struct ILogProvider *CStandardSetupLogFilter::CreateObject(void)
{
  struct ILogProvider *result; // rax

  result = (struct ILogProvider *)operator new(0x18u);
  if ( result )
  {
    *((_DWORD *)result + 2) = -1;
    *(_QWORD *)result = &CStandardSetupLogFilter::`vftable';
    *(_QWORD *)((char *)result + 12) = 0x4000000;
    *((_DWORD *)result + 5) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800204d0  sub     rsp, 28h
0x1800204d4  mov     ecx, 18h; Size
0x1800204d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800204de  mov     [rsp+28h+arg_0], rax
0x1800204e3  test    rax, rax
0x1800204e6  jz      short loc_180020508
0x1800204e8  lea     rcx, ??_7CStandardSetupLogFilter@@6B@; const CStandardSetupLogFilter::`vftable'
0x1800204ef  mov     dword ptr [rax+8], 0FFFFFFFFh
0x1800204f6  mov     [rax], rcx
0x1800204f9  mov     qword ptr [rax+0Ch], 4000000h
0x180020501  mov     dword ptr [rax+14h], 1
0x180020508  add     rsp, 28h
0x18002050c  retn
```
