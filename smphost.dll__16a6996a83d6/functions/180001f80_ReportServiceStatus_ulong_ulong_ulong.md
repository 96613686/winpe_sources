# ReportServiceStatus(ulong,ulong,ulong)

- ea: `0x180001f80`
- end: `0x180001fe7`
- name: `?ReportServiceStatus@@YAXKKK@Z`
- size: `103`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002000`
- `0x180002044`
- `0x180002380`
- `0x1800024f0`

## callees

- `0x180001f80`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001fe0`

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
0x180001f80  xor     eax, eax
0x180001f82  mov     cs:dword_1800067D4, ecx
0x180001f88  mov     cs:dword_1800067DC, eax
0x180001f8e  mov     cs:dword_1800067E8, r8d
0x180001f95  cmp     ecx, 2
0x180001f98  jnz     short loc_180001FA2
0x180001f9a  mov     cs:dword_1800067D8, eax
0x180001fa0  jmp     short loc_180001FB6
0x180001fa2  mov     cs:dword_1800067D8, 1
0x180001fac  cmp     ecx, 4
0x180001faf  jz      short loc_180001FCC
0x180001fb1  cmp     ecx, 1
0x180001fb4  jz      short loc_180001FCC
0x180001fb6  mov     eax, cs:dword_180006210
0x180001fbc  mov     cs:dword_1800067E4, eax
0x180001fc2  inc     eax
0x180001fc4  mov     cs:dword_180006210, eax
0x180001fca  jmp     short loc_180001FD2
0x180001fcc  mov     cs:dword_1800067E4, eax
0x180001fd2  mov     rcx, cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_ServiceStatusHandle
0x180001fd9  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS g_ServiceStatus
0x180001fe0  jmp     cs:__imp_SetServiceStatus
```
