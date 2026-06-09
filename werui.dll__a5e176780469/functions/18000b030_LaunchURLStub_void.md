# LaunchURLStub(void *)

- ea: `0x18000b030`
- end: `0x18000b0de`
- name: `?LaunchURLStub@@YAKPEAX@Z`
- size: `174`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800035dc`
- `0x18000afbc`
- `0x18000b030`
- `0x18000b82c`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x18000b0d7`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18000b0d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LaunchURLStub(SHELLEXECUTEINFOW *Parameter)
{
  HMODULE v3; // rdi
  SHELLEXECUTEINFOW *v4; // [rsp+30h] [rbp+8h] BYREF

  if ( Parameter )
  {
    v4 = Parameter;
    if ( (int)UtilSafeLaunchURL(Parameter) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids);
    }
    v3 = *(HMODULE *)&Parameter[1].cbSize;
    *(_QWORD *)&Parameter[1].cbSize = 0;
    utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(&v4);
    if ( v3 )
      FreeLibraryAndExitThread(v3, 0);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b030  mov     [rsp+arg_8], rbx
0x18000b035  push    rdi
0x18000b036  sub     rsp, 20h
0x18000b03a  mov     rbx, rcx
0x18000b03d  test    rcx, rcx
0x18000b040  jnz     short loc_18000B07B
0x18000b042  lea     rax, WPP_GLOBAL_Control
0x18000b049  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b050  cmp     rcx, rax
0x18000b053  jz      short loc_18000B06E
0x18000b055  test    byte ptr [rcx+1Ch], 1
0x18000b059  jz      short loc_18000B06E
0x18000b05b  lea     edx, [rbx+10h]
0x18000b05e  lea     r8, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids
0x18000b065  mov     rcx, [rcx+10h]
0x18000b069  call    WPP_SF_
0x18000b06e  xor     eax, eax
0x18000b070  mov     rbx, [rsp+28h+arg_8]
0x18000b075  add     rsp, 20h
0x18000b079  pop     rdi
0x18000b07a  retn
0x18000b07b  mov     [rsp+28h+arg_0], rbx
0x18000b080  call    ?UtilSafeLaunchURL@@YAJPEAU_SHELLEXECUTEINFOW@@@Z; UtilSafeLaunchURL(_SHELLEXECUTEINFOW *)
0x18000b085  test    eax, eax
0x18000b087  jns     short loc_18000B0B7
0x18000b089  lea     rax, WPP_GLOBAL_Control
0x18000b090  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b097  cmp     rcx, rax
0x18000b09a  jz      short loc_18000B0B7
0x18000b09c  test    byte ptr [rcx+1Ch], 1
0x18000b0a0  jz      short loc_18000B0B7
0x18000b0a2  mov     edx, 11h
0x18000b0a7  lea     r8, WPP_84e0403860003c8b7f85a224b3bf7818_Traceguids
0x18000b0ae  mov     rcx, [rcx+10h]
0x18000b0b2  call    WPP_SF_
0x18000b0b7  mov     rdi, [rbx+70h]
0x18000b0bb  mov     qword ptr [rbx+70h], 0
0x18000b0c3  lea     rcx, [rsp+28h+arg_0]
0x18000b0c8  call    ??1?$unique_ptr@ULAUNCH_URL_PARAMETERS@@U?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>::~unique_ptr<LAUNCH_URL_PARAMETERS,utl::default_delete<LAUNCH_URL_PARAMETERS>>(void)
0x18000b0cd  test    rdi, rdi
0x18000b0d0  jz      short loc_18000B06E
0x18000b0d2  xor     edx, edx; dwExitCode
0x18000b0d4  mov     rcx, rdi; hLibModule
0x18000b0d7  call    cs:__imp_FreeLibraryAndExitThread
```
