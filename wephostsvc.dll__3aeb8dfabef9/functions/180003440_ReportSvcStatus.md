# ReportSvcStatus

- ea: `0x180003440`
- end: `0x1800034ad`
- name: `ReportSvcStatus`
- size: `109`
- prototype: `BOOL __fastcall(int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800030b8`
- `0x1800034c0`
- `0x1800035f0`

## callees

- `0x180003440`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800034a6`

## pseudocode

```c
BOOL __fastcall ReportSvcStatus(int a1, int a2, int a3)
{
  dword_18000875C = a1;
  dword_180008764 = a2;
  dword_180008770 = a3;
  if ( a1 == 2 )
  {
    dword_180008760 = 0;
  }
  else
  {
    dword_180008760 = 1;
    if ( a1 == 4 || a1 == 1 )
    {
      dword_18000876C = 0;
      return SetServiceStatus((SERVICE_STATUS_HANDLE)qword_180008778, (LPSERVICE_STATUS)&dword_180008758);
    }
  }
  dword_18000876C = dword_180008790++;
  return SetServiceStatus((SERVICE_STATUS_HANDLE)qword_180008778, (LPSERVICE_STATUS)&dword_180008758);
}

```

## disassembly

```asm
0x180003440  mov     cs:dword_18000875C, ecx
0x180003446  mov     cs:dword_180008764, edx
0x18000344c  mov     cs:dword_180008770, r8d
0x180003453  cmp     ecx, 2
0x180003456  jnz     short loc_180003464
0x180003458  mov     cs:dword_180008760, 0
0x180003462  jmp     short loc_180003478
0x180003464  mov     cs:dword_180008760, 1
0x18000346e  cmp     ecx, 4
0x180003471  jz      short loc_18000348E
0x180003473  cmp     ecx, 1
0x180003476  jz      short loc_18000348E
0x180003478  mov     eax, cs:dword_180008790
0x18000347e  mov     cs:dword_18000876C, eax
0x180003484  inc     eax
0x180003486  mov     cs:dword_180008790, eax
0x18000348c  jmp     short loc_180003498
0x18000348e  mov     cs:dword_18000876C, 0
0x180003498  mov     rcx, cs:qword_180008778
0x18000349f  lea     rdx, dword_180008758
0x1800034a6  jmp     cs:__imp_SetServiceStatus
```
