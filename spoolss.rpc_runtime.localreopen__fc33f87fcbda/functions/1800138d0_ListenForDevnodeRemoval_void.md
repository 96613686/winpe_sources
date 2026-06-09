# ListenForDevnodeRemoval(void)

- ea: `0x1800138d0`
- end: `0x1800139a9`
- name: `?ListenForDevnodeRemoval@@YAJXZ`
- size: `217`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013b00`

## callees

- `0x180005680`
- `0x1800138d0`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180013978`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180013978`

## pseudocode

```c
__int64 ListenForDevnodeRemoval(void)
{
  __int64 result; // rax
  struct HDEVQUERY__ *v1; // [rsp+58h] [rbp+7h] BYREF
  int v2; // [rsp+60h] [rbp+Fh] BYREF
  DEVPROPKEY v3; // [rsp+68h] [rbp+17h]
  int v4; // [rsp+7Ch] [rbp+2Bh]
  __int64 v5; // [rsp+80h] [rbp+2Fh]
  int v6; // [rsp+88h] [rbp+37h]
  int v7; // [rsp+8Ch] [rbp+3Bh]
  const wchar_t *v8; // [rsp+90h] [rbp+3Fh]

  result = 0;
  if ( !g_hDevQuery )
  {
    v1 = 0;
    v3 = DEVPKEY_Device_HardwareIds;
    v2 = 4096;
    v8 = L"PRINTENUM\\PrinterConnection";
    v4 = 0;
    v5 = 0;
    v6 = 18;
    v7 = 56;
    result = DevCreateObjectQuery(3, 1, 0, 0, 1, &v2, DevnodeRemovalCallback, 0, &v1);
    if ( (int)result >= 0 )
      g_hDevQuery = v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800138d0  mov     r11, rsp
0x1800138d3  push    rbp
0x1800138d4  lea     rbp, [r11-5Fh]
0x1800138d8  sub     rsp, 0A0h
0x1800138df  mov     rax, cs:__security_cookie
0x1800138e6  xor     rax, rsp
0x1800138e9  mov     [rbp+57h+var_10], rax
0x1800138ed  xor     eax, eax
0x1800138ef  cmp     cs:?g_hDevQuery@@3PEAUHDEVQUERY__@@EA, rax; HDEVQUERY__ * g_hDevQuery
0x1800138f6  jnz     loc_180013993
0x1800138fc  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x180013903  mov     [rbp+57h+var_50], rax
0x180013907  mov     edx, 1
0x18001390c  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x180013912  xor     r9d, r9d
0x180013915  mov     [rbp+57h+var_30], eax
0x180013918  xor     r8d, r8d
0x18001391b  lea     rax, aPrintenumPrint; "PRINTENUM\\PrinterConnection"
0x180013922  mov     [rbp+57h+var_48], 1000h
0x180013929  mov     [rbp+57h+var_18], rax
0x18001392d  lea     ecx, [rdx+2]
0x180013930  lea     rax, [rbp+57h+var_50]
0x180013934  mov     [rbp+57h+var_2C], 0
0x18001393b  mov     [r11-68h], rax
0x18001393f  lea     rax, ?DevnodeRemovalCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevnodeRemovalCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180013946  mov     qword ptr [r11-70h], 0
0x18001394e  mov     [r11-78h], rax
0x180013952  lea     rax, [rbp+57h+var_48]
0x180013956  mov     [r11-80h], rax
0x18001395a  mov     [rsp+20h], edx
0x18001395e  movups  [rbp+57h+var_40], xmm0
0x180013962  mov     [rbp+57h+var_28], 0
0x18001396a  mov     [rbp+57h+var_20], 12h
0x180013971  mov     [rbp+57h+var_1C], 38h ; '8'
0x180013978  call    cs:__imp_DevCreateObjectQuery
0x18001397f  nop     dword ptr [rax+rax+00h]
0x180013984  test    eax, eax
0x180013986  js      short loc_180013993
0x180013988  mov     rcx, [rbp+57h+var_50]
0x18001398c  mov     cs:?g_hDevQuery@@3PEAUHDEVQUERY__@@EA, rcx; HDEVQUERY__ * g_hDevQuery
0x180013993  mov     rcx, [rbp+57h+var_10]
0x180013997  xor     rcx, rsp; StackCookie
0x18001399a  call    __security_check_cookie
0x18001399f  add     rsp, 0A0h
0x1800139a6  pop     rbp
0x1800139a7  retn
```
