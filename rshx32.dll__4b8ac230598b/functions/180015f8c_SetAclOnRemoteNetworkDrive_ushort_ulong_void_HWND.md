# SetAclOnRemoteNetworkDrive(ushort *,ulong,void *,HWND__ *)

- ea: `0x180015f8c`
- end: `0x180016065`
- name: `?SetAclOnRemoteNetworkDrive@@YAHPEAGKPEAXPEAUHWND__@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(unsigned __int16 *, char, void *, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007950`

## callees

- `0x18000c444`
- `0x180015f8c`
- `0x180019404`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180015fdd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180015fdd`

## pseudocode

```c
__int64 __fastcall SetAclOnRemoteNetworkDrive(unsigned __int16 *a1, char a2, void *a3, HWND a4)
{
  char v7; // bp
  int v8; // ebx
  DWORD v10[10]; // [rsp+30h] [rbp-28h] BYREF
  WORD v11; // [rsp+60h] [rbp+8h] BYREF

  v7 = (char)a1;
  if ( a1 && a3 )
  {
    v8 = a2 & 0xC;
    if ( (a2 & 0xC) == 0 )
      return 1;
    v11 = 0;
    v10[0] = 0;
    if ( GetSecurityDescriptorControl(a3, &v11, v10) )
    {
      if ( (a2 & 4) != 0 && (v11 & 0x1000) != 0 || (a2 & 8) != 0 && (v11 & 0x2000) != 0 )
        return 1;
      if ( (unsigned int)MsgPopup(a4, 56 - (unsigned int)((a2 & 4) != 0), 0x57u, 0x10134u, g_hInstance, v7) != 7 )
      {
        ProtectACLs(v8, a3);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015f8c  mov     r11, rsp
0x180015f8f  mov     [r11+10h], rbx
0x180015f93  mov     [r11+18h], rbp
0x180015f97  push    rsi
0x180015f98  push    rdi
0x180015f99  push    r14
0x180015f9b  sub     rsp, 40h
0x180015f9f  mov     r14, r9
0x180015fa2  mov     rsi, r8
0x180015fa5  mov     edi, edx
0x180015fa7  mov     rbp, rcx
0x180015faa  test    rcx, rcx
0x180015fad  jz      loc_180016050
0x180015fb3  test    r8, r8
0x180015fb6  jz      loc_180016050
0x180015fbc  mov     ebx, edx
0x180015fbe  and     ebx, 0Ch
0x180015fc1  jz      loc_180016049
0x180015fc7  xor     eax, eax
0x180015fc9  lea     r8, [r11-28h]; lpdwRevision
0x180015fcd  lea     rdx, [r11+8]; pControl
0x180015fd1  mov     [rsp+58h+arg_0], ax
0x180015fd6  mov     rcx, rsi; pSecurityDescriptor
0x180015fd9  mov     [rsp+58h+var_28], eax
0x180015fdd  call    cs:__imp_GetSecurityDescriptorControl
0x180015fe3  test    eax, eax
0x180015fe5  jz      short loc_180016050
0x180015fe7  mov     eax, edi
0x180015fe9  and     eax, 4
0x180015fec  jz      short loc_180015FFA
0x180015fee  mov     ecx, 1000h
0x180015ff3  test    [rsp+58h+arg_0], cx
0x180015ff8  jnz     short loc_180016049
0x180015ffa  test    dil, 8
0x180015ffe  jz      short loc_18001600C
0x180016000  mov     ecx, 2000h
0x180016005  test    [rsp+58h+arg_0], cx
0x18001600a  jnz     short loc_180016049
0x18001600c  neg     eax
0x18001600e  mov     qword ptr [rsp+58h+var_30], rbp; char
0x180016013  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18001601a  mov     r9d, 10134h; uType
0x180016020  sbb     rdx, rdx
0x180016023  mov     [rsp+58h+hAppInst], rax; hAppInst
0x180016028  add     rdx, 38h ; '8'; unsigned int
0x18001602c  mov     r8d, 57h ; 'W'; unsigned int
0x180016032  mov     rcx, r14; hWnd
0x180016035  call    MsgPopup
0x18001603a  cmp     eax, 7
0x18001603d  jz      short loc_180016050
0x18001603f  mov     rdx, rsi; void *
0x180016042  mov     ecx, ebx; unsigned int
0x180016044  call    ?ProtectACLs@@YAXKPEAX@Z; ProtectACLs(ulong,void *)
0x180016049  mov     eax, 1
0x18001604e  jmp     short loc_180016052
0x180016050  xor     eax, eax
0x180016052  mov     rbx, [rsp+58h+arg_8]
0x180016057  mov     rbp, [rsp+58h+arg_10]
0x18001605c  add     rsp, 40h
0x180016060  pop     r14
0x180016062  pop     rdi
0x180016063  pop     rsi
0x180016064  retn
```
