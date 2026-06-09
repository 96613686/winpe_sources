# CInfraCreateTask::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180024f80`
- end: `0x1800250b3`
- name: `?CanRunTask@CInfraCreateTask@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023054`
- `0x180024f80`
- `0x18002d80e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fde`

## pseudocode

```c
__int64 __fastcall CInfraCreateTask::CanRunTask(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  char *v11; // rax
  char *v12; // rbx
  unsigned int v13; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 14, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
  }
  *(_QWORD *)(a1 + 72) = a8;
  v11 = (char *)CoTaskMemAlloc(0x60u);
  v12 = v11;
  if ( v11 )
  {
    v13 = 0;
    memset_0(v11 + 8, 0, 0x58u);
    *(_DWORD *)v12 = 96;
    *((_DWORD *)v12 + 1) = 16388;
    *((_QWORD *)v12 + 2) = hModule;
    *((_QWORD *)v12 + 1) = a2;
    *((_QWORD *)v12 + 3) = 102;
    *((_QWORD *)v12 + 4) = 10902;
  }
  else
  {
    v13 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 15, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
    }
  }
  *a9 = v12;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
  }
  return v13;
}

```

## disassembly

```asm
0x180024f80  push    rbx
0x180024f82  push    rsi
0x180024f83  push    rdi
0x180024f84  push    r15
0x180024f86  sub     rsp, 28h
0x180024f8a  mov     rsi, rdx
0x180024f8d  mov     rbx, rcx
0x180024f90  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f97  lea     r15, WPP_GLOBAL_Control
0x180024f9e  cmp     rcx, r15
0x180024fa1  jz      short loc_180024FCD
0x180024fa3  cmp     byte ptr [rcx+91h], 4
0x180024faa  jb      short loc_180024FCD
0x180024fac  test    byte ptr [rcx+94h], 1
0x180024fb3  jz      short loc_180024FCD
0x180024fb5  mov     rcx, [rcx+88h]
0x180024fbc  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x180024fc3  mov     edx, 0Eh
0x180024fc8  call    WPP_SF_
0x180024fcd  mov     rax, [rsp+48h+arg_38]
0x180024fd5  mov     ecx, 60h ; '`'; cb
0x180024fda  mov     [rbx+48h], rax
0x180024fde  call    cs:__imp_CoTaskMemAlloc
0x180024fe4  mov     rbx, rax
0x180024fe7  test    rax, rax
0x180024fea  jz      short loc_18002502B
0x180024fec  xor     edi, edi
0x180024fee  lea     rcx, [rax+8]; void *
0x180024ff2  xor     edx, edx; Val
0x180024ff4  lea     r8d, [rdi+58h]; Size
0x180024ff8  call    memset_0
0x180024ffd  mov     dword ptr [rbx], 60h ; '`'
0x180025003  mov     dword ptr [rbx+4], 4004h
0x18002500a  mov     rcx, cs:hModule
0x180025011  mov     [rbx+10h], rcx
0x180025015  mov     [rbx+8], rsi
0x180025019  mov     qword ptr [rbx+18h], 66h ; 'f'
0x180025021  mov     qword ptr [rbx+20h], 2A96h
0x180025029  jmp     short loc_180025066
0x18002502b  mov     edi, 8007000Eh
0x180025030  mov     rcx, cs:WPP_GLOBAL_Control
0x180025037  cmp     rcx, r15
0x18002503a  jz      short loc_180025066
0x18002503c  cmp     byte ptr [rcx+91h], 1
0x180025043  jb      short loc_180025066
0x180025045  test    byte ptr [rcx+94h], 1
0x18002504c  jz      short loc_180025066
0x18002504e  mov     rcx, [rcx+88h]
0x180025055  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x18002505c  mov     edx, 0Fh
0x180025061  call    WPP_SF_
0x180025066  mov     rax, [rsp+48h+arg_40]
0x18002506e  mov     [rax], rbx
0x180025071  mov     rcx, cs:WPP_GLOBAL_Control
0x180025078  cmp     rcx, r15
0x18002507b  jz      short loc_1800250A7
0x18002507d  cmp     byte ptr [rcx+91h], 4
0x180025084  jb      short loc_1800250A7
0x180025086  test    byte ptr [rcx+94h], 1
0x18002508d  jz      short loc_1800250A7
0x18002508f  mov     rcx, [rcx+88h]
0x180025096  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x18002509d  mov     edx, 10h
0x1800250a2  call    WPP_SF_
0x1800250a7  mov     eax, edi
0x1800250a9  add     rsp, 28h
0x1800250ad  pop     r15
0x1800250af  pop     rdi
0x1800250b0  pop     rsi
0x1800250b1  pop     rbx
0x1800250b2  retn
```
