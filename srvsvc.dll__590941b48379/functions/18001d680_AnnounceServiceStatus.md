# AnnounceServiceStatus

- ea: `0x18001d680`
- end: `0x18001d762`
- name: `AnnounceServiceStatus`
- size: `226`
- prototype: `int __fastcall(int)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011a70`
- `0x180023a00`
- `0x180023c00`
- `0x18002c750`
- `0x18002db40`

## callees

- `0x18001d680`
- `0x180020dc0`
- `0x18002d490`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d757`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d757`

## pseudocode

```c
int __fastcall AnnounceServiceStatus(int a1)
{
  SERVICE_STATUS_HANDLE v1; // r8
  _UNKNOWN **v2; // rax

  v1 = SsServiceStatusHandle;
  if ( SsServiceStatusHandle )
  {
    if ( SsServiceStatus.dwCurrentState != 4 || !a1 )
    {
      SsServiceStatus.dwCheckPoint += a1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_LLLLLL(*((_QWORD *)WPP_GLOBAL_Control + 2));
        v1 = SsServiceStatusHandle;
      }
      LODWORD(v2) = SetServiceStatus(v1, &SsServiceStatus);
    }
  }
  else
  {
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      LODWORD(v2) = WPP_SF_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (unsigned int)((_DWORD)SsServiceStatusHandle + 33),
                      WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x18001d680  sub     rsp, 58h
0x18001d684  mov     r8, cs:SsServiceStatusHandle
0x18001d68b  test    r8, r8
0x18001d68e  jnz     short loc_18001D6D3
0x18001d690  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d697  lea     rax, WPP_GLOBAL_Control
0x18001d69e  cmp     rcx, rax
0x18001d6a1  jz      loc_18001D75D
0x18001d6a7  test    byte ptr [rcx+1Ch], 1
0x18001d6ab  jz      loc_18001D75D
0x18001d6b1  cmp     byte ptr [rcx+19h], 1
0x18001d6b5  jb      loc_18001D75D
0x18001d6bb  mov     rcx, [rcx+10h]
0x18001d6bf  lea     edx, [r8+21h]
0x18001d6c3  lea     r8, WPP_65c5d25a675637bc3f250135bb92ff22_Traceguids
0x18001d6ca  add     rsp, 58h
0x18001d6ce  jmp     WPP_SF_
0x18001d6d3  mov     r9d, cs:SsServiceStatus.dwCurrentState
0x18001d6da  cmp     r9d, 4
0x18001d6de  jnz     short loc_18001D6E4
0x18001d6e0  test    ecx, ecx
0x18001d6e2  jnz     short loc_18001D75D
0x18001d6e4  mov     edx, cs:SsServiceStatus.dwCheckPoint
0x18001d6ea  add     edx, ecx
0x18001d6ec  mov     cs:SsServiceStatus.dwCheckPoint, edx
0x18001d6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6f9  lea     rax, WPP_GLOBAL_Control
0x18001d700  cmp     rcx, rax
0x18001d703  jz      short loc_18001D74D
0x18001d705  test    byte ptr [rcx+1Ch], 1
0x18001d709  jz      short loc_18001D74D
0x18001d70b  cmp     byte ptr [rcx+19h], 1
0x18001d70f  jb      short loc_18001D74D
0x18001d711  mov     eax, cs:SsServiceStatus.dwWaitHint
0x18001d717  mov     rcx, [rcx+10h]
0x18001d71b  mov     [rsp+58h+var_18], eax
0x18001d71f  mov     eax, cs:SsServiceStatus.dwServiceSpecificExitCode
0x18001d725  mov     [rsp+58h+var_20], edx
0x18001d729  mov     [rsp+58h+var_28], eax
0x18001d72d  mov     eax, cs:SsServiceStatus.dwWin32ExitCode
0x18001d733  mov     [rsp+58h+var_30], eax
0x18001d737  mov     eax, cs:SsServiceStatus.dwControlsAccepted
0x18001d73d  mov     [rsp+58h+var_38], eax
0x18001d741  call    WPP_SF_LLLLLL
0x18001d746  mov     r8, cs:SsServiceStatusHandle
0x18001d74d  lea     rdx, SsServiceStatus; lpServiceStatus
0x18001d754  mov     rcx, r8; hServiceStatus
0x18001d757  call    cs:__imp_SetServiceStatus
0x18001d75d  add     rsp, 58h
0x18001d761  retn
```
