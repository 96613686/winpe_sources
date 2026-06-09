# ReportServiceStatus(ulong,ulong,ulong)

- ea: `0x180001f3c`
- end: `0x180001fa3`
- name: `?ReportServiceStatus@@YAXKKK@Z`
- size: `103`
- prototype: `void __fastcall(unsigned int, __int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180001fb0`
- `0x180001fec`
- `0x180002300`
- `0x180002460`

## callees

- `0x180001f3c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001f9c`

## pseudocode

```c
void __fastcall ReportServiceStatus(unsigned int a1, __int64 a2, int a3)
{
  dword_1800067D4 = a1;
  dword_1800067DC = 0;
  dword_1800067E8 = a3;
  if ( a1 == 2 )
  {
    dword_1800067D8 = 0;
  }
  else
  {
    dword_1800067D8 = 1;
    if ( a1 == 4 || a1 == 1 )
    {
      dword_1800067E4 = 0;
      goto LABEL_7;
    }
  }
  dword_1800067E4 = dword_180006210++;
LABEL_7:
  SetServiceStatus(g_ServiceStatusHandle, &g_ServiceStatus);
}

```

## disassembly

```asm
0x180001f3c  xor     eax, eax
0x180001f3e  mov     cs:dword_1800067D4, ecx
0x180001f44  mov     cs:dword_1800067DC, eax
0x180001f4a  mov     cs:dword_1800067E8, r8d
0x180001f51  cmp     ecx, 2
0x180001f54  jnz     short loc_180001F5E
0x180001f56  mov     cs:dword_1800067D8, eax
0x180001f5c  jmp     short loc_180001F72
0x180001f5e  mov     cs:dword_1800067D8, 1
0x180001f68  cmp     ecx, 4
0x180001f6b  jz      short loc_180001F88
0x180001f6d  cmp     ecx, 1
0x180001f70  jz      short loc_180001F88
0x180001f72  mov     eax, cs:dword_180006210
0x180001f78  mov     cs:dword_1800067E4, eax
0x180001f7e  inc     eax
0x180001f80  mov     cs:dword_180006210, eax
0x180001f86  jmp     short loc_180001F8E
0x180001f88  mov     cs:dword_1800067E4, eax
0x180001f8e  mov     rcx, cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_ServiceStatusHandle
0x180001f95  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS g_ServiceStatus
0x180001f9c  jmp     cs:__imp_SetServiceStatus
```
