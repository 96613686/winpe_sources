# CSdController::_ClearNetShareTargetSpaceInfo(void)

- ea: `0x1800114b8`
- end: `0x1800115d3`
- name: `?_ClearNetShareTargetSpaceInfo@CSdController@@AEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x1800114b8`
- `0x18001586c`
- `0x180015974`
- `0x18001b544`
- `0x18001eccc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001150e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001150e`

## pseudocode

```c
__int64 __fastcall CSdController::_ClearNetShareTargetSpaceInfo(CSdController *this)
{
  LSTATUS v1; // eax
  int v2; // edx
  int v3; // r8d
  int v4; // r9d
  signed int v5; // ebx
  __int16 v6; // ax
  signed int v8; // [rsp+30h] [rbp-40h] BYREF
  __int16 v9; // [rsp+34h] [rbp-3Ch]
  __int16 v10; // [rsp+36h] [rbp-3Ah]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF

  hKey = (HKEY)this;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v8,
    "CSdController::_ClearNetShareTargetSpaceInfo",
    2498,
    1);
  hKey = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams\\TargetDevice",
         0,
         0x2001Fu,
         &hKey);
  v5 = v1;
  if ( v1 > 0 )
    v5 = (unsigned __int16)v1 | 0x80070000;
  v8 = v5;
  v6 = 2502;
  if ( v5 < 0 )
    goto LABEL_4;
  v9 = 2502;
  v5 = SetRegKeyVirtualization(hKey, v2, v3, v4);
  v8 = v5;
  v6 = 2503;
  if ( v5 < 0 )
    goto LABEL_4;
  v9 = 2503;
  v5 = SxRegWriteULONGLONG(hKey, L"TotalSize", 0);
  v8 = v5;
  v6 = 2506;
  if ( v5 < 0 || (v9 = 2506, v5 = SxRegWriteULONGLONG(hKey, L"Freespace", 0), v8 = v5, v6 = 2507, v5 < 0) )
LABEL_4:
    v10 = v6;
  else
    v9 = 2507;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800114b8  mov     [rsp-8+arg_8], rbx
0x1800114bd  mov     [rsp-8+hKey], rcx
0x1800114c2  push    rbp
0x1800114c3  mov     rbp, rsp
0x1800114c6  sub     rsp, 70h
0x1800114ca  mov     r9d, 1; unsigned __int16
0x1800114d0  lea     rdx, aCsdcontrollerC_2; "CSdController::_ClearNetShareTargetSpac"...
0x1800114d7  mov     r8d, 9C2h; unsigned __int16
0x1800114dd  lea     rcx, [rbp+var_40]; this
0x1800114e1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800114e6  lea     rax, [rbp+hKey]
0x1800114ea  mov     [rbp+hKey], 0
0x1800114f2  mov     r9d, 2001Fh; samDesired
0x1800114f8  mov     [rsp+70h+phkResult], rax; phkResult
0x1800114fd  xor     r8d, r8d; ulOptions
0x180011500  lea     rdx, c_wszSafedocsDeviceTargetKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180011507  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001150e  call    cs:__imp_RegOpenKeyExW
0x180011514  mov     ebx, eax
0x180011516  test    eax, eax
0x180011518  jle     short loc_180011523
0x18001151a  movzx   ebx, ax
0x18001151d  or      ebx, 80070000h
0x180011523  mov     [rbp+var_40], ebx
0x180011526  mov     eax, 9C6h
0x18001152b  test    ebx, ebx
0x18001152d  jns     short loc_180011535
0x18001152f  mov     [rbp+var_3A], ax
0x180011533  jmp     short loc_18001159E
0x180011535  mov     rcx, [rbp+hKey]; KeyHandle
0x180011539  mov     [rbp+var_3C], ax
0x18001153d  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x180011542  mov     ebx, eax
0x180011544  mov     [rbp+var_40], eax
0x180011547  test    eax, eax
0x180011549  mov     eax, 9C7h
0x18001154e  js      short loc_18001152F
0x180011550  mov     rcx, [rbp+hKey]; hKey
0x180011554  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x18001155b  xor     r8d, r8d; unsigned __int64
0x18001155e  mov     [rbp+var_3C], ax
0x180011562  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x180011567  mov     ebx, eax
0x180011569  mov     [rbp+var_40], eax
0x18001156c  test    eax, eax
0x18001156e  mov     eax, 9CAh
0x180011573  js      short loc_18001152F
0x180011575  mov     rcx, [rbp+hKey]; hKey
0x180011579  lea     rdx, c_wszSafedocsDeviceFree; "Freespace"
0x180011580  xor     r8d, r8d; unsigned __int64
0x180011583  mov     [rbp+var_3C], ax
0x180011587  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001158c  mov     ebx, eax
0x18001158e  mov     [rbp+var_40], eax
0x180011591  test    eax, eax
0x180011593  mov     eax, 9CBh
0x180011598  js      short loc_18001152F
0x18001159a  mov     [rbp+var_3C], ax
0x18001159e  mov     rcx, [rbp+hKey]; hKey
0x1800115a2  lea     rdx, [rcx-1]
0x1800115a6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800115aa  ja      short loc_1800115BA
0x1800115ac  call    cs:__imp_RegCloseKey
0x1800115b2  mov     [rbp+hKey], 0
0x1800115ba  lea     rcx, [rbp+var_40]; this
0x1800115be  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800115c3  mov     eax, ebx
0x1800115c5  mov     rbx, [rsp+70h+arg_8]
0x1800115cd  add     rsp, 70h
0x1800115d1  pop     rbp
0x1800115d2  retn
```
