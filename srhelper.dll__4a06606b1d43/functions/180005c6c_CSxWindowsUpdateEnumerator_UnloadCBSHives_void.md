# CSxWindowsUpdateEnumerator::_UnloadCBSHives(void)

- ea: `0x180005c6c`
- end: `0x180005de7`
- name: `?_UnloadCBSHives@CSxWindowsUpdateEnumerator@@AEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(CSxWindowsUpdateEnumerator *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000408c`
- `0x1800055a4`

## callees

- `0x180003ce0`
- `0x180003d08`
- `0x18000508c`
- `0x180005c6c`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`

## import_xrefs

- `ADVAPI32!RegUnLoadKeyW` at `0x180005d24`
- `ADVAPI32!RegUnLoadKeyW` at `0x180005d24`

## string_xrefs

- `0x180005cb7`: `CSxWindowsUpdateEnumerator::_UnloadCBSHives`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_UnloadCBSHives(CSxWindowsUpdateEnumerator *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rax
  signed int v5; // ebx
  unsigned int v6; // edi
  __int16 v7; // ax
  __int64 v9; // r12
  unsigned int v10; // r14d
  __int64 v11; // r15
  LPCWSTR *v12; // rsi
  LSTATUS KeyW; // eax
  int v14; // ebp
  signed int v15; // [rsp+30h] [rbp-88h] BYREF
  __int16 v16; // [rsp+34h] [rbp-84h]
  __int16 v17; // [rsp+36h] [rbp-82h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CSxWindowsUpdateEnumerator::_UnloadCBSHives", 266);
  v4 = *(_QWORD *)this;
  v5 = 0;
  v6 = *(_DWORD *)(v4 + 16);
  if ( v6 )
  {
    v9 = *(_QWORD *)(v4 + 8);
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = (LPCWSTR *)(v9 + 24 * v11);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, v12[1]);
      if ( KeyW )
      {
        v5 = KeyW > 0 ? (unsigned __int16)KeyW | 0x80070000 : KeyW;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_012e94a410f034635dd5ee797f3d6253_Traceguids,
            (unsigned int)v12[1],
            v5);
        }
      }
      if ( *v12 )
      {
        v14 = SxDeleteFile(*v12);
        if ( v14 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
          {
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_012e94a410f034635dd5ee797f3d6253_Traceguids,
              (unsigned int)*v12,
              v5);
          }
          v5 = v14;
        }
      }
      CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation((LPVOID *)(v9 + 24 * v11));
      ++v10;
      ++v11;
    }
    while ( v10 < v6 );
    v15 = v5;
    v7 = 306;
    if ( v5 < 0 )
    {
      v17 = 306;
      goto LABEL_7;
    }
  }
  else
  {
    v15 = 0;
    v7 = 277;
  }
  v16 = v7;
LABEL_7:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, v2, v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005c6c  push    rbx
0x180005c6e  push    rbp
0x180005c6f  push    rsi
0x180005c70  push    rdi
0x180005c71  push    r12
0x180005c73  push    r13
0x180005c75  push    r14
0x180005c77  push    r15
0x180005c79  sub     rsp, 78h
0x180005c7d  mov     rbx, rcx
0x180005c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c87  lea     r13, WPP_GLOBAL_Control
0x180005c8e  cmp     rcx, r13
0x180005c91  jz      short loc_180005CB1
0x180005c93  test    dword ptr [rcx+1Ch], 20000000h
0x180005c9a  jz      short loc_180005CB1
0x180005c9c  mov     rcx, [rcx+10h]
0x180005ca0  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180005ca7  mov     edx, 0Ch
0x180005cac  call    WPP_SF_
0x180005cb1  mov     r8d, 10Ah; unsigned __int16
0x180005cb7  lea     rdx, aCsxwindowsupda_3; "CSxWindowsUpdateEnumerator::_UnloadCBSH"...
0x180005cbe  lea     rcx, [rsp+0B8h+var_88]; this
0x180005cc3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005cc8  mov     rax, [rbx]
0x180005ccb  xor     ebx, ebx
0x180005ccd  mov     edi, [rax+10h]
0x180005cd0  test    edi, edi
0x180005cd2  jnz     short loc_180005CFF
0x180005cd4  mov     [rsp+0B8h+var_88], ebx
0x180005cd8  mov     eax, 115h
0x180005cdd  mov     [rsp+0B8h+var_84], ax
0x180005ce2  lea     rcx, [rsp+0B8h+var_88]; this
0x180005ce7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180005cec  mov     eax, ebx
0x180005cee  add     rsp, 78h
0x180005cf2  pop     r15
0x180005cf4  pop     r14
0x180005cf6  pop     r13
0x180005cf8  pop     r12
0x180005cfa  pop     rdi
0x180005cfb  pop     rsi
0x180005cfc  pop     rbp
0x180005cfd  pop     rbx
0x180005cfe  retn
0x180005cff  mov     r12, [rax+8]
0x180005d03  xor     r14d, r14d
0x180005d06  test    edi, edi
0x180005d08  jz      loc_180005DCC
0x180005d0e  xor     r15d, r15d
0x180005d11  lea     rax, [r15+r15*2]
0x180005d15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005d1c  lea     rsi, [r12+rax*8]
0x180005d20  mov     rdx, [rsi+8]; lpSubKey
0x180005d24  call    cs:__imp_RegUnLoadKeyW
0x180005d2a  test    eax, eax
0x180005d2c  jz      short loc_180005D6F
0x180005d2e  jg      short loc_180005D34
0x180005d30  mov     ebx, eax
0x180005d32  jmp     short loc_180005D3D
0x180005d34  movzx   ebx, ax
0x180005d37  or      ebx, 80070000h
0x180005d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d44  cmp     rcx, r13
0x180005d47  jz      short loc_180005D6F
0x180005d49  test    dword ptr [rcx+1Ch], 4000000h
0x180005d50  jz      short loc_180005D6F
0x180005d52  mov     r9, [rsi+8]
0x180005d56  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180005d5d  mov     rcx, [rcx+10h]
0x180005d61  mov     edx, 0Dh
0x180005d66  mov     [rsp+0B8h+var_98], ebx
0x180005d6a  call    WPP_SF_SD
0x180005d6f  mov     rcx, [rsi]; lpFileName
0x180005d72  test    rcx, rcx
0x180005d75  jz      short loc_180005DB5
0x180005d77  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180005d7c  mov     ebp, eax
0x180005d7e  test    eax, eax
0x180005d80  jns     short loc_180005DB5
0x180005d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d89  cmp     rcx, r13
0x180005d8c  jz      short loc_180005DB3
0x180005d8e  test    dword ptr [rcx+1Ch], 4000000h
0x180005d95  jz      short loc_180005DB3
0x180005d97  mov     r9, [rsi]
0x180005d9a  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180005da1  mov     rcx, [rcx+10h]
0x180005da5  mov     edx, 0Eh
0x180005daa  mov     [rsp+0B8h+var_98], ebx
0x180005dae  call    WPP_SF_SD
0x180005db3  mov     ebx, ebp
0x180005db5  mov     rcx, rsi; struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *
0x180005db8  call    ?_FreeCbsHiveLoadInformation@CSxWindowsUpdateEnumerator@@SAXPEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z; CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)
0x180005dbd  inc     r14d
0x180005dc0  inc     r15
0x180005dc3  cmp     r14d, edi
0x180005dc6  jb      loc_180005D11
0x180005dcc  mov     [rsp+0B8h+var_88], ebx
0x180005dd0  mov     eax, 132h
0x180005dd5  test    ebx, ebx
0x180005dd7  jns     loc_180005CDD
0x180005ddd  mov     [rsp+0B8h+var_82], ax
0x180005de2  jmp     loc_180005CE2
```
