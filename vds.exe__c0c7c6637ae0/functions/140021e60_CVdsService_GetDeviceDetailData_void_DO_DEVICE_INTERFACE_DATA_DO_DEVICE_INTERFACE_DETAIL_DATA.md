# CVdsService::GetDeviceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *)

- ea: `0x140021e60`
- end: `0x14002201a`
- name: `?GetDeviceDetailData@CVdsService@@AEAAJPEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, void *, struct _DO_DEVICE_INTERFACE_DATA *, struct _DO_DEVICE_INTERFACE_DETAIL_DATA **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140023f58`
- `0x140027890`

## callees

- `0x140021e60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021f29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f8b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140021ee7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140021f81`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140021ee7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140021f81`
- `vdsutil!VdsHeapAlloc` at `0x140021f3c`
- `vdsutil!VdsHeapAlloc` at `0x140021f3c`
- `vdsutil!VdsTraceW` at `0x140021e93`
- `vdsutil!VdsTraceW` at `0x140021f19`
- `vdsutil!VdsTraceW` at `0x140021fc5`
- `vdsutil!VdsTraceW` at `0x140021fea`
- `vdsutil!VdsTraceW` at `0x140021fff`
- `vdsutil!VdsTraceW` at `0x140021e93`
- `vdsutil!VdsTraceW` at `0x140021f19`
- `vdsutil!VdsTraceW` at `0x140021fc5`
- `vdsutil!VdsTraceW` at `0x140021fea`
- `vdsutil!VdsTraceW` at `0x140021fff`

## string_xrefs

- `0x140021ff3`: `EXIT CVdsService::GetDeviceDetailData, hr=%lX`
- `0x140021fa0`: `CVdsService::GetDeviceDetailData, 4, hr=%lX`
- `0x140021f0d`: `CVdsService::GetDeviceDetailData, 2, hr=%lX`
- `0x140021e81`: `CVdsService::GetDeviceDetailData`
- `0x140021fdc`: `CVdsService::GetDeviceDetailData, 1, hDevInfo=%p, pDeviceIntfData=%p, ppDetailData=%p`
- `0x140021f4f`: `CVdsService::GetDeviceDetailData, 3, hr=%lX`
- `0x140021fb7`: `CVdsService::GetDeviceDetailData, 5`

## pseudocode

```c
__int64 __fastcall CVdsService::GetDeviceDetailData(
        CVdsService *this,
        char *a2,
        struct _DO_DEVICE_INTERFACE_DATA *a3,
        struct _DO_DEVICE_INTERFACE_DETAIL_DATA **a4)
{
  signed int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v11; // rax
  _WORD *v12; // r8
  signed int LastError; // eax
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+54h] [rbp+Ch]

  v16 = HIDWORD(this);
  v15 = 0;
  VdsTraceW(2, L"CVdsService::GetDeviceDetailData");
  if ( (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a3 && a4 )
  {
    *a4 = 0;
    v15 = 0;
    DevObjGetDeviceInterfaceDetail(a2, a3, 0, 0, &v15, 0);
    if ( GetLastError() == 122 )
    {
      v9 = v15;
      ProcessHeap = GetProcessHeap();
      v11 = (struct _DO_DEVICE_INTERFACE_DETAIL_DATA *)VdsHeapAlloc(ProcessHeap, 8, v9);
      *a4 = v11;
      if ( v11 )
      {
        *(_DWORD *)v11 = 8;
        v12 = *a4;
        v15 = 0;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(a2, a3, v12, v9, &v15, 0) )
        {
          if ( *((_WORD *)*a4 + 2) )
          {
            v8 = 0;
          }
          else
          {
            v8 = -2147211505;
            VdsTraceW(0, L"CVdsService::GetDeviceDetailData, 5");
          }
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          VdsTraceW(0, L"CVdsService::GetDeviceDetailData, 4, hr=%lX", v8);
        }
      }
      else
      {
        v8 = -2147024882;
        VdsTraceW(0, L"CVdsService::GetDeviceDetailData, 3, hr=%lX", 2147942414LL);
      }
    }
    else
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      VdsTraceW(0, L"CVdsService::GetDeviceDetailData, 2, hr=%lX", v8);
    }
  }
  else
  {
    v8 = -2147024809;
    VdsTraceW(0, L"CVdsService::GetDeviceDetailData, 1, hDevInfo=%p, pDeviceIntfData=%p, ppDetailData=%p", a2, a3, a4);
  }
  VdsTraceW(2, L"EXIT CVdsService::GetDeviceDetailData, hr=%lX", v8);
  return v8;
}

```

## disassembly

```asm
0x140021e60  mov     rax, rsp
0x140021e63  mov     [rax+10h], rbx
0x140021e67  mov     [rax+18h], rbp
0x140021e6b  mov     [rax+8], rcx
0x140021e6f  push    rsi
0x140021e70  push    rdi
0x140021e71  push    r14
0x140021e73  sub     rsp, 30h
0x140021e77  mov     rbp, rdx
0x140021e7a  mov     dword ptr [rax+8], 0
0x140021e81  lea     rdx, aCvdsserviceGet_24; "CVdsService::GetDeviceDetailData"
0x140021e88  mov     ecx, 2
0x140021e8d  mov     rdi, r9
0x140021e90  mov     rsi, r8
0x140021e93  call    cs:__imp_VdsTraceW
0x140021e99  lea     rax, [rbp-1]
0x140021e9d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021ea1  ja      loc_140021FD1
0x140021ea7  test    rsi, rsi
0x140021eaa  jz      loc_140021FD1
0x140021eb0  test    rdi, rdi
0x140021eb3  jz      loc_140021FD1
0x140021eb9  lea     rax, [rsp+48h+arg_0]
0x140021ebe  mov     [rsp+48h+var_20], 0
0x140021ec7  xor     r9d, r9d
0x140021eca  mov     [rsp+48h+var_28], rax
0x140021ecf  xor     r8d, r8d
0x140021ed2  mov     qword ptr [rdi], 0
0x140021ed9  mov     rdx, rsi
0x140021edc  mov     [rsp+48h+arg_0], 0
0x140021ee4  mov     rcx, rbp
0x140021ee7  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x140021eed  call    cs:__imp_GetLastError
0x140021ef3  cmp     eax, 7Ah ; 'z'
0x140021ef6  jz      short loc_140021F24
0x140021ef8  call    cs:__imp_GetLastError
0x140021efe  mov     ebx, eax
0x140021f00  test    eax, eax
0x140021f02  jle     short loc_140021F0D
0x140021f04  movzx   ebx, ax
0x140021f07  or      ebx, 80070000h
0x140021f0d  lea     rdx, aCvdsserviceGet_36; "CVdsService::GetDeviceDetailData, 2, hr"...
0x140021f14  mov     r8d, ebx
0x140021f17  xor     ecx, ecx
0x140021f19  call    cs:__imp_VdsTraceW
0x140021f1f  jmp     loc_140021FF0
0x140021f24  mov     r14d, [rsp+48h+arg_0]
0x140021f29  call    cs:__imp_GetProcessHeap
0x140021f2f  mov     ebx, 8
0x140021f34  mov     r8d, r14d
0x140021f37  mov     rcx, rax
0x140021f3a  mov     edx, ebx
0x140021f3c  call    cs:__imp_VdsHeapAlloc
0x140021f42  mov     [rdi], rax
0x140021f45  test    rax, rax
0x140021f48  jnz     short loc_140021F58
0x140021f4a  mov     ebx, 8007000Eh
0x140021f4f  lea     rdx, aCvdsserviceGet_35; "CVdsService::GetDeviceDetailData, 3, hr"...
0x140021f56  jmp     short loc_140021F14
0x140021f58  mov     [rax], ebx
0x140021f5a  mov     r9d, r14d
0x140021f5d  mov     r8, [rdi]
0x140021f60  lea     rax, [rsp+48h+arg_0]
0x140021f65  mov     [rsp+48h+var_20], 0
0x140021f6e  mov     rdx, rsi
0x140021f71  mov     rcx, rbp
0x140021f74  mov     [rsp+48h+var_28], rax
0x140021f79  mov     [rsp+48h+arg_0], 0
0x140021f81  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x140021f87  test    eax, eax
0x140021f89  jnz     short loc_140021FAC
0x140021f8b  call    cs:__imp_GetLastError
0x140021f91  mov     ebx, eax
0x140021f93  test    eax, eax
0x140021f95  jle     short loc_140021FA0
0x140021f97  movzx   ebx, ax
0x140021f9a  or      ebx, 80070000h
0x140021fa0  lea     rdx, aCvdsserviceGet_137; "CVdsService::GetDeviceDetailData, 4, hr"...
0x140021fa7  jmp     loc_140021F14
0x140021fac  mov     rcx, [rdi]
0x140021faf  xor     eax, eax
0x140021fb1  cmp     ax, [rcx+4]
0x140021fb5  jnz     short loc_140021FCD
0x140021fb7  lea     rdx, aCvdsserviceGet_101; "CVdsService::GetDeviceDetailData, 5"
0x140021fbe  xor     ecx, ecx
0x140021fc0  mov     ebx, 8004270Fh
0x140021fc5  call    cs:__imp_VdsTraceW
0x140021fcb  jmp     short loc_140021FF0
0x140021fcd  xor     ebx, ebx
0x140021fcf  jmp     short loc_140021FF0
0x140021fd1  mov     r9, rsi
0x140021fd4  mov     [rsp+48h+var_28], rdi
0x140021fd9  mov     r8, rbp
0x140021fdc  lea     rdx, aCvdsserviceGet_129; "CVdsService::GetDeviceDetailData, 1, hD"...
0x140021fe3  xor     ecx, ecx
0x140021fe5  mov     ebx, 80070057h
0x140021fea  call    cs:__imp_VdsTraceW
0x140021ff0  mov     r8d, ebx
0x140021ff3  lea     rdx, aExitCvdsservic_2; "EXIT CVdsService::GetDeviceDetailData, "...
0x140021ffa  mov     ecx, 2
0x140021fff  call    cs:__imp_VdsTraceW
0x140022005  mov     rbp, [rsp+48h+arg_10]
0x14002200a  mov     eax, ebx
0x14002200c  mov     rbx, [rsp+48h+arg_8]
0x140022011  add     rsp, 30h
0x140022015  pop     r14
0x140022017  pop     rdi
0x140022018  pop     rsi
0x140022019  retn
```
