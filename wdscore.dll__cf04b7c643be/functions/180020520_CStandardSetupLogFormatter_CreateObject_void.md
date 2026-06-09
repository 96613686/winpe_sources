# CStandardSetupLogFormatter::CreateObject(void)

- ea: `0x180020520`
- end: `0x18002055a`
- name: `?CreateObject@CStandardSetupLogFormatter@@SAPEAVILogProvider@@XZ`
- size: `58`
- prototype: `struct ILogProvider *(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180001144`
- `0x180020520`

## pseudocode

```c
struct ILogProvider *CStandardSetupLogFormatter::CreateObject(void)
{
  struct ILogProvider *result; // rax

  result = (struct ILogProvider *)operator new(0x20u);
  if ( result )
  {
    *(_QWORD *)result = &CStandardSetupLogFormatter::`vftable';
    *((_DWORD *)result + 2) = -1;
    *((_DWORD *)result + 3) = -1;
    *((_DWORD *)result + 4) = -1;
    *((_DWORD *)result + 5) = -1;
    *((_DWORD *)result + 6) = -1;
  }
  return result;
}

```

## disassembly

```asm
0x180020520  sub     rsp, 28h
0x180020524  mov     ecx, 20h ; ' '; Size
0x180020529  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002052e  mov     [rsp+28h+arg_0], rax
0x180020533  test    rax, rax
0x180020536  jz      short loc_180020554
0x180020538  lea     rcx, ??_7CStandardSetupLogFormatter@@6B@; const CStandardSetupLogFormatter::`vftable'
0x18002053f  mov     [rax], rcx
0x180020542  or      ecx, 0FFFFFFFFh
0x180020545  mov     [rax+8], ecx
0x180020548  mov     [rax+0Ch], ecx
0x18002054b  mov     [rax+10h], ecx
0x18002054e  mov     [rax+14h], ecx
0x180020551  mov     [rax+18h], ecx
0x180020554  add     rsp, 28h
0x180020558  retn
```
