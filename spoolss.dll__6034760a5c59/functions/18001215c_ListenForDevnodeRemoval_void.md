# ListenForDevnodeRemoval(void)

- ea: `0x18001215c`
- end: `0x18001222e`
- name: `?ListenForDevnodeRemoval@@YAJXZ`
- size: `210`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012380`

## callees

- `0x180005320`
- `0x18001215c`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180012204`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180012204`

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
0x18001215c  mov     r11, rsp
0x18001215f  push    rbp
0x180012160  lea     rbp, [r11-5Fh]
0x180012164  sub     rsp, 0A0h
0x18001216b  mov     rax, cs:__security_cookie
0x180012172  xor     rax, rsp
0x180012175  mov     [rbp+57h+var_10], rax
0x180012179  xor     eax, eax
0x18001217b  cmp     cs:?g_hDevQuery@@3PEAUHDEVQUERY__@@EA, rax; HDEVQUERY__ * g_hDevQuery
0x180012182  jnz     loc_180012219
0x180012188  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x18001218f  mov     [rbp+57h+var_50], rax
0x180012193  mov     edx, 1
0x180012198  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x18001219e  xor     r9d, r9d
0x1800121a1  mov     [rbp+57h+var_30], eax
0x1800121a4  xor     r8d, r8d
0x1800121a7  lea     rax, aPrintenumPrint; "PRINTENUM\\PrinterConnection"
0x1800121ae  mov     [rbp+57h+var_48], 1000h
0x1800121b5  mov     [rbp+57h+var_18], rax
0x1800121b9  lea     ecx, [rdx+2]
0x1800121bc  lea     rax, [rbp+57h+var_50]
0x1800121c0  mov     [rbp+57h+var_2C], 0
0x1800121c7  mov     [r11-68h], rax
0x1800121cb  lea     rax, ?DevnodeRemovalCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevnodeRemovalCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800121d2  mov     qword ptr [r11-70h], 0
0x1800121da  mov     [r11-78h], rax
0x1800121de  lea     rax, [rbp+57h+var_48]
0x1800121e2  mov     [r11-80h], rax
0x1800121e6  mov     [rsp+20h], edx
0x1800121ea  movups  [rbp+57h+var_40], xmm0
0x1800121ee  mov     [rbp+57h+var_28], 0
0x1800121f6  mov     [rbp+57h+var_20], 12h
0x1800121fd  mov     [rbp+57h+var_1C], 38h ; '8'
0x180012204  call    cs:__imp_DevCreateObjectQuery
0x18001220a  test    eax, eax
0x18001220c  js      short loc_180012219
0x18001220e  mov     rcx, [rbp+57h+var_50]
0x180012212  mov     cs:?g_hDevQuery@@3PEAUHDEVQUERY__@@EA, rcx; HDEVQUERY__ * g_hDevQuery
0x180012219  mov     rcx, [rbp+57h+var_10]
0x18001221d  xor     rcx, rsp; StackCookie
0x180012220  call    __security_check_cookie
0x180012225  add     rsp, 0A0h
0x18001222c  pop     rbp
0x18001222d  retn
```
