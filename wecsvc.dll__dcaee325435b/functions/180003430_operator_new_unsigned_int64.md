# operator new(unsigned __int64)

- ea: `0x180003430`
- end: `0x1800034e4`
- name: `??2@YAPEAX_K@Z`
- size: `180`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `42`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180001dbc`
- `0x180002694`
- `0x180003840`
- `0x180003ea0`
- `0x180004434`
- `0x180004608`
- `0x180004760`
- `0x180004b80`
- `0x1800052cc`
- `0x180005ad0`
- `0x180005ec8`
- `0x180005f68`
- `0x1800061b0`
- `0x180009170`
- `0x18000a938`
- `0x18000ada0`
- `0x18000ff3c`
- `0x18001050c`
- `0x18001054c`
- `0x18001058c`
- `0x1800105d8`
- `0x180010780`
- `0x180010800`
- `0x180010894`
- `0x180013450`
- `0x180013794`
- `0x18001415c`
- `0x1800153c0`
- `0x180015b88`
- `0x180018d48`
- `0x180018d88`
- `0x180018e28`
- `0x18001926c`
- `0x180019308`
- `0x18001c1f8`
- `0x18001c244`
- `0x18001e24c`
- `0x18001e2fc`
- `0x18001e41c`
- `0x18001e5e8`
- `0x18001f258`
- `0x180020bc2`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003430`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003439`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003439`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003447`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003447`

## string_xrefs

- `0x18000348e`: `admin\wmi\events\forwarding\collector\service\localloc.cpp`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rax
  LPVOID result; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v5; // [rsp+28h] [rbp-40h]
  const char *v6; // [rsp+30h] [rbp-38h]
  __int64 v7; // [rsp+38h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, dwBytes);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dac8dede4c2536856c898b51fde0ebd6_Traceguids, 14);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\collector\\service\\localloc.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = 14;
    v10 = -1;
    v11 = 13;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180003430  push    rbx
0x180003432  sub     rsp, 60h
0x180003436  mov     rbx, rcx
0x180003439  call    cs:__imp_GetProcessHeap
0x18000343f  mov     r8, rbx; dwBytes
0x180003442  xor     edx, edx; dwFlags
0x180003444  mov     rcx, rax; hHeap
0x180003447  call    cs:__imp_HeapAlloc
0x18000344d  xor     ebx, ebx
0x18000344f  test    rax, rax
0x180003452  jnz     loc_1800034DE
0x180003458  mov     rcx, cs:WPP_GLOBAL_Control
0x18000345f  lea     rax, WPP_GLOBAL_Control
0x180003466  cmp     rcx, rax
0x180003469  jz      short loc_18000348E
0x18000346b  test    byte ptr [rcx+1Ch], 10h
0x18000346f  jz      short loc_18000348E
0x180003471  cmp     byte ptr [rcx+19h], 2
0x180003475  jb      short loc_18000348E
0x180003477  mov     rcx, [rcx+10h]
0x18000347b  lea     edx, [rbx+0Ah]
0x18000347e  lea     r9d, [rbx+0Eh]
0x180003482  lea     r8, WPP_dac8dede4c2536856c898b51fde0ebd6_Traceguids
0x180003489  call    WPP_SF_D
0x18000348e  lea     rax, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180003495  mov     [rsp+68h+var_40], bl
0x180003499  mov     [rsp+68h+var_38], rax
0x18000349e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800034a5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800034ac  mov     [rsp+68h+var_30], rbx
0x1800034b1  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800034b6  mov     [rsp+68h+pExceptionObject], rax
0x1800034bb  mov     [rsp+68h+var_28], rbx
0x1800034c0  mov     [rsp+68h+var_20], 0Eh
0x1800034c8  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x1800034d0  mov     [rsp+68h+var_18], 0Dh
0x1800034d8  call    _CxxThrowException_0
0x1800034de  add     rsp, 60h
0x1800034e2  pop     rbx
0x1800034e3  retn
```
