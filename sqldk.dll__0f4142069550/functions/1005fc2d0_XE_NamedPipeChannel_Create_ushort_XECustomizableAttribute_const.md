# XE_NamedPipeChannel::Create(ushort,XECustomizableAttribute const *)

- ea: `0x1005fc2d0`
- end: `0x1005fc4c9`
- name: `?Create@XE_NamedPipeChannel@@SAPEAVXE_IProxySessionTransport@@GPEBUXECustomizableAttribute@@@Z`
- size: `505`
- prototype: `struct XE_IProxySessionTransport *__fastcall(unsigned __int16, const struct XECustomizableAttribute *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1005fca00`

## callees

- `0x1004425f0`
- `0x1005fc2d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1005fc447`
- `KERNEL32!CreateFileW` at `0x1005fc447`
- `KERNEL32!lstrcmpW` at `0x1005fc3f2`
- `KERNEL32!lstrcmpW` at `0x1005fc41a`
- `KERNEL32!lstrcmpW` at `0x1005fc3f2`
- `KERNEL32!lstrcmpW` at `0x1005fc41a`
- `KERNEL32!SetNamedPipeHandleState` at `0x1005fc47a`
- `KERNEL32!SetNamedPipeHandleState` at `0x1005fc47a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
struct XE_IProxySessionTransport *__fastcall XE_NamedPipeChannel::Create(
        __int16 a1,
        const struct XECustomizableAttribute *a2)
{
  __int64 v2; // r15
  _DWORD *v3; // rbx
  const struct XECustomizableAttribute *Attr; // rax
  const WCHAR *v5; // r14
  const struct XECustomizableAttribute *v6; // rax
  const WCHAR *v7; // rbp
  const struct XECustomizableAttribute *v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rdi
  HANDLE FileW; // rax
  __int16 v13; // [rsp+48h] [rbp-50h] BYREF
  const struct XECustomizableAttribute *v14; // [rsp+50h] [rbp-48h]
  void *Mode; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v16; // [rsp+B0h] [rbp+18h]
  __int64 v17; // [rsp+B8h] [rbp+20h]

  v2 = 0;
  v3 = 0;
  v16 = 0;
  v13 = a1;
  if ( !a2 )
    v13 = 0;
  v14 = a2;
  Attr = XE_CustomizableAttributes::GetAttr((XE_CustomizableAttributes *)&v13, L"xe_namedpipe_channel_name");
  if ( Attr )
    v5 = (const WCHAR *)*((_QWORD *)Attr + 2);
  else
    v5 = 0;
  v6 = XE_CustomizableAttributes::GetAttr((XE_CustomizableAttributes *)&v13, L"xe_namedpipe_role");
  if ( v6 )
    v7 = (const WCHAR *)*((_QWORD *)v6 + 2);
  else
    v7 = 0;
  v8 = XE_CustomizableAttributes::GetAttr((XE_CustomizableAttributes *)&v13, L"xe_namedpipe_handle");
  if ( v8 )
    v9 = *((_QWORD *)v8 + 2);
  else
    v9 = -1;
  if ( v7 && v5 )
  {
    Mode = &XE_API::sm_ServiceAPI;
    v10 = qword_100714F08(0, 32);
    v17 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = &XE_IProxySessionTransport::`vftable';
      *(_DWORD *)(v10 + 8) = 1;
      *(_QWORD *)v10 = &XE_NamedPipeChannel::`vftable';
      *(_QWORD *)(v10 + 16) = -1;
      *(_BYTE *)(v10 + 28) = 0;
    }
    else
    {
      v10 = 0;
    }
    v3 = (_DWORD *)v10;
    v16 = v10;
    if ( v10 )
    {
      if ( !lstrcmpW(v7, L"server") )
      {
        if ( v9 == -1 )
          goto LABEL_25;
        *(_QWORD *)(v10 + 16) = v9;
        *(_DWORD *)(v10 + 24) = 0;
        goto LABEL_24;
      }
      if ( !lstrcmpW(v7, L"client") )
      {
        FileW = CreateFileW(v5, 0xC0000000, 0, 0, 3u, 0x80u, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          *(_QWORD *)(v10 + 16) = FileW;
          *(_DWORD *)(v10 + 24) = 1;
          LODWORD(Mode) = 2;
          if ( SetNamedPipeHandleState(FileW, (LPDWORD)&Mode, 0, 0) )
          {
LABEL_24:
            v3 = 0;
            v16 = 0;
            v2 = v10;
          }
        }
      }
    }
  }
LABEL_25:
  Mode = v3;
  if ( v3 )
  {
    v3[2] = -2147426643;
    qword_100714F10(v3);
  }
  return (struct XE_IProxySessionTransport *)v2;
}

```

## disassembly

```asm
0x1005fc2d0  mov     rax, rsp
0x1005fc2d3  push    rbx
0x1005fc2d4  push    rbp
0x1005fc2d5  push    rsi
0x1005fc2d6  push    rdi
0x1005fc2d7  push    r12
0x1005fc2d9  push    r14
0x1005fc2db  push    r15
0x1005fc2dd  sub     rsp, 60h
0x1005fc2e1  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1005fc2e9  xor     r12d, r12d
0x1005fc2ec  mov     r15d, r12d
0x1005fc2ef  mov     ebx, r12d
0x1005fc2f2  mov     [rax+18h], rbx
0x1005fc2f6  test    rdx, rdx
0x1005fc2f9  mov     [rax-50h], cx
0x1005fc2fd  jnz     short loc_1005FC304
0x1005fc2ff  mov     [rax-50h], r12w
0x1005fc304  mov     [rsp+98h+var_48], rdx
0x1005fc309  lea     rdx, aXeNamedpipeCha; "xe_namedpipe_channel_name"
0x1005fc310  lea     rcx, [rsp+98h+var_50]; this
0x1005fc315  call    ?GetAttr@XE_CustomizableAttributes@@QEBAQEBUXECustomizableAttribute@@QEB_W@Z; XE_CustomizableAttributes::GetAttr(wchar_t const * const)
0x1005fc31a  test    rax, rax
0x1005fc31d  jz      short loc_1005FC325
0x1005fc31f  mov     r14, [rax+10h]
0x1005fc323  jmp     short loc_1005FC328
0x1005fc325  mov     r14, r12
0x1005fc328  lea     rdx, aXeNamedpipeRol; "xe_namedpipe_role"
0x1005fc32f  lea     rcx, [rsp+98h+var_50]; this
0x1005fc334  call    ?GetAttr@XE_CustomizableAttributes@@QEBAQEBUXECustomizableAttribute@@QEB_W@Z; XE_CustomizableAttributes::GetAttr(wchar_t const * const)
0x1005fc339  test    rax, rax
0x1005fc33c  jz      short loc_1005FC344
0x1005fc33e  mov     rbp, [rax+10h]
0x1005fc342  jmp     short loc_1005FC347
0x1005fc344  mov     rbp, r12
0x1005fc347  lea     rdx, aXeNamedpipeHan; "xe_namedpipe_handle"
0x1005fc34e  lea     rcx, [rsp+98h+var_50]; this
0x1005fc353  call    ?GetAttr@XE_CustomizableAttributes@@QEBAQEBUXECustomizableAttribute@@QEB_W@Z; XE_CustomizableAttributes::GetAttr(wchar_t const * const)
0x1005fc358  test    rax, rax
0x1005fc35b  jz      short loc_1005FC363
0x1005fc35d  mov     rsi, [rax+10h]
0x1005fc361  jmp     short loc_1005FC36A
0x1005fc363  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1005fc36a  test    rbp, rbp
0x1005fc36d  jz      loc_1005FC492
0x1005fc373  test    r14, r14
0x1005fc376  jz      loc_1005FC492
0x1005fc37c  lea     rax, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x1005fc383  mov     [rsp+98h+Mode], rax
0x1005fc38b  mov     edx, 20h ; ' '
0x1005fc390  xor     ecx, ecx
0x1005fc392  call    cs:qword_100714F08
0x1005fc398  mov     rdi, rax
0x1005fc39b  mov     [rsp+98h+arg_18], rax
0x1005fc3a3  test    rax, rax
0x1005fc3a6  jz      short loc_1005FC3D1
0x1005fc3a8  lea     rax, ??_7XE_IProxySessionTransport@@6B@; const XE_IProxySessionTransport::`vftable'
0x1005fc3af  mov     [rdi], rax
0x1005fc3b2  mov     dword ptr [rdi+8], 1
0x1005fc3b9  lea     rax, ??_7XE_NamedPipeChannel@@6B@; const XE_NamedPipeChannel::`vftable'
0x1005fc3c0  mov     [rdi], rax
0x1005fc3c3  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1005fc3cb  mov     byte ptr [rdi+1Ch], 0
0x1005fc3cf  jmp     short loc_1005FC3D4
0x1005fc3d1  mov     rdi, r12
0x1005fc3d4  mov     rbx, rdi
0x1005fc3d7  mov     [rsp+98h+arg_10], rbx
0x1005fc3df  test    rdi, rdi
0x1005fc3e2  jz      loc_1005FC492
0x1005fc3e8  lea     rdx, aServer; "server"
0x1005fc3ef  mov     rcx, rbp; lpString1
0x1005fc3f2  call    cs:__imp_lstrcmpW
0x1005fc3f8  test    eax, eax
0x1005fc3fa  jnz     short loc_1005FC410
0x1005fc3fc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1005fc400  jz      loc_1005FC492
0x1005fc406  mov     [rdi+10h], rsi
0x1005fc40a  mov     [rdi+18h], r12d
0x1005fc40e  jmp     short loc_1005FC484
0x1005fc410  lea     rdx, aClient; "client"
0x1005fc417  mov     rcx, rbp; lpString1
0x1005fc41a  call    cs:__imp_lstrcmpW
0x1005fc420  test    eax, eax
0x1005fc422  jnz     short loc_1005FC492
0x1005fc424  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x1005fc429  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1005fc431  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x1005fc439  xor     r9d, r9d; lpSecurityAttributes
0x1005fc43c  xor     r8d, r8d; dwShareMode
0x1005fc43f  mov     edx, 0C0000000h; dwDesiredAccess
0x1005fc444  mov     rcx, r14; lpFileName
0x1005fc447  call    cs:__imp_CreateFileW
0x1005fc44d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005fc451  jz      short loc_1005FC492
0x1005fc453  mov     [rdi+10h], rax
0x1005fc457  mov     dword ptr [rdi+18h], 1
0x1005fc45e  mov     dword ptr [rsp+98h+Mode], 2
0x1005fc469  xor     r9d, r9d; lpCollectDataTimeout
0x1005fc46c  xor     r8d, r8d; lpMaxCollectionCount
0x1005fc46f  lea     rdx, [rsp+98h+Mode]; lpMode
0x1005fc477  mov     rcx, rax; hNamedPipe
0x1005fc47a  call    cs:__imp_SetNamedPipeHandleState
0x1005fc480  test    eax, eax
0x1005fc482  jz      short loc_1005FC492
0x1005fc484  mov     rbx, r12
0x1005fc487  mov     [rsp+98h+arg_10], rbx
0x1005fc48f  mov     r15, rdi
0x1005fc492  mov     [rsp+98h+Mode], rbx
0x1005fc49a  test    rbx, rbx
0x1005fc49d  jz      short loc_1005FC4AF
0x1005fc49f  mov     dword ptr [rbx+8], 8000DEADh
0x1005fc4a6  mov     rcx, rbx
0x1005fc4a9  call    cs:qword_100714F10
0x1005fc4af  mov     [rsp+98h+arg_10], r12
0x1005fc4b7  mov     rax, r15
0x1005fc4ba  add     rsp, 60h
0x1005fc4be  pop     r15
0x1005fc4c0  pop     r14
0x1005fc4c2  pop     r12
0x1005fc4c4  pop     rdi
0x1005fc4c5  pop     rsi
0x1005fc4c6  pop     rbp
0x1005fc4c7  pop     rbx
0x1005fc4c8  retn
```
