# ServiceMain(ulong,ushort * *)

- ea: `0x1800034c0`
- end: `0x18000355c`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `156`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800030b8`
- `0x180003440`
- `0x1800034c0`
- `0x180003960`
- `0x180003be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003536`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003536`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int inited; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  int v6; // [rsp+30h] [rbp-38h] BYREF
  char v7[16]; // [rsp+38h] [rbp-30h] BYREF
  int *v8; // [rsp+48h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp-18h]

  inited = InitService();
  if ( inited >= 0 )
  {
    ReportSvcStatus(4, 0, 0);
    WaitForSingleObject(hObject, 0xFFFFFFFF);
    v5 = 0;
  }
  else
  {
    if ( (Microsoft_Windows_WEPHOSTSVCEnableBits & 1) != 0 )
    {
      v6 = inited;
      v9 = 4;
      v8 = &v6;
      McGenEventWrite_EventWriteTransfer(v3, ServiceFailure, v4, 2, v7);
    }
    v5 = 1064;
  }
  ReportSvcStatus(1, v5, 0);
}

```

## disassembly

```asm
0x1800034c0  sub     rsp, 68h
0x1800034c4  mov     rax, cs:__security_cookie
0x1800034cb  xor     rax, rsp
0x1800034ce  mov     [rsp+68h+var_10], rax
0x1800034d3  call    ?InitService@@YAJXZ; InitService(void)
0x1800034d8  test    eax, eax
0x1800034da  jns     short loc_18000351F
0x1800034dc  test    cs:Microsoft_Windows_WEPHOSTSVCEnableBits, 1
0x1800034e3  jz      short loc_180003518
0x1800034e5  mov     [rsp+68h+var_38], eax
0x1800034e9  lea     rdx, ServiceFailure
0x1800034f0  lea     rax, [rsp+68h+var_38]
0x1800034f5  mov     [rsp+68h+var_18], 4
0x1800034fe  mov     [rsp+68h+var_20], rax
0x180003503  mov     r9d, 2
0x180003509  lea     rax, [rsp+68h+var_30]
0x18000350e  mov     [rsp+68h+var_48], rax
0x180003513  call    McGenEventWrite_EventWriteTransfer
0x180003518  mov     edx, 428h
0x18000351d  jmp     short loc_18000353E
0x18000351f  xor     edx, edx
0x180003521  xor     r8d, r8d
0x180003524  lea     ecx, [rdx+4]
0x180003527  call    ReportSvcStatus
0x18000352c  mov     rcx, cs:hObject; hHandle
0x180003533  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003536  call    cs:__imp_WaitForSingleObject
0x18000353c  xor     edx, edx
0x18000353e  xor     r8d, r8d
0x180003541  lea     ecx, [r8+1]
0x180003545  call    ReportSvcStatus
0x18000354a  mov     rcx, [rsp+68h+var_10]
0x18000354f  xor     rcx, rsp; StackCookie
0x180003552  call    __security_check_cookie
0x180003557  add     rsp, 68h
0x18000355b  retn
```
