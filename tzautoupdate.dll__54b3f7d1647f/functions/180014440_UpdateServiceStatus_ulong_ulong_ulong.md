# UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x180014440`
- end: `0x1800144a4`
- name: `?UpdateServiceStatus@@YAXKKK@Z`
- size: `100`
- prototype: `void __fastcall(int, __int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800140a0`
- `0x1800143a0`

## callees

- `0x180014440`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001449d`

## pseudocode

```c
void __fastcall UpdateServiceStatus(int a1, __int64 a2, int a3)
{
  LODWORD(xmmword_180031364) = a1;
  DWORD2(xmmword_180031364) = 0;
  HIDWORD(qword_180031374) = a3;
  DWORD1(xmmword_180031364) = a1 != 2;
  if ( a1 == 4 || a1 == 1 )
    LODWORD(qword_180031374) = 0;
  else
    LODWORD(qword_180031374) = dword_180030A14++;
  SetServiceStatus(gSvcStatusHandle, &gSvcStatus);
}

```

## disassembly

```asm
0x180014440  xor     eax, eax
0x180014442  mov     dword ptr cs:xmmword_180031364, ecx
0x180014448  cmp     ecx, 2
0x18001444b  mov     dword ptr cs:xmmword_180031364+8, 0
0x180014455  mov     dword ptr cs:qword_180031374+4, r8d
0x18001445c  setnz   al
0x18001445f  mov     dword ptr cs:xmmword_180031364+4, eax
0x180014465  cmp     ecx, 4
0x180014468  jz      short loc_180014485
0x18001446a  cmp     ecx, 1
0x18001446d  jz      short loc_180014485
0x18001446f  mov     eax, cs:dword_180030A14
0x180014475  mov     dword ptr cs:qword_180031374, eax
0x18001447b  inc     eax
0x18001447d  mov     cs:dword_180030A14, eax
0x180014483  jmp     short loc_18001448F
0x180014485  mov     dword ptr cs:qword_180031374, 0
0x18001448f  mov     rcx, cs:?gSvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * gSvcStatusHandle
0x180014496  lea     rdx, ?gSvcStatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS gSvcStatus
0x18001449d  jmp     cs:__imp_SetServiceStatus
```
