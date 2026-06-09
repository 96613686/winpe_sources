# FlushVolume(_FLT_FILTER *,_FLT_INSTANCE *)

- ea: `0x14000dd90`
- end: `0x14000df13`
- name: `?FlushVolume@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@@Z`
- size: `387`
- prototype: `int(struct _FLT_FILTER *, struct _FLT_INSTANCE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140003554`

## callees

- `0x14000d8a8`
- `0x14000d9c4`
- `0x14000dd90`
- `0x14000f684`
- `0x14000f900`
- `0x14000fd40`

## import_xrefs

- `FLTMGR!FltGetVolumeName` at `0x14000de2d`
- `FLTMGR!FltGetVolumeName` at `0x14000de2d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14000ddf8`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14000ddf8`
- `FLTMGR!FltClose` at `0x14000ded6`
- `FLTMGR!FltClose` at `0x14000ded6`
- `FLTMGR!FltObjectDereference` at `0x14000deec`
- `FLTMGR!FltObjectDereference` at `0x14000deec`

## string_xrefs

- `0x14000de8e`: `WinSetupMon::FlushVolume: CreateFile failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall FlushVolume(struct _FLT_FILTER *a1, struct _FLT_INSTANCE *a2)
{
  struct _FLT_FILTER *v2; // rdi
  NTSTATUS VolumeFromInstance; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  int v7; // eax
  unsigned __int8 v8; // dl
  HANDLE v9; // rdi
  int v10; // eax
  unsigned int v12; // [rsp+28h] [rbp-D8h]
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[128]; // [rsp+70h] [rbp-90h] BYREF

  v2 = (struct _FLT_FILTER *)FilterHandle;
  RetVolume = 0;
  memset(v16, 0, sizeof(v16));
  *(_QWORD *)&VolumeName.Length = 0x800000;
  VolumeName.Buffer = (wchar_t *)v16;
  FileHandle = 0;
  VolumeFromInstance = FltGetVolumeFromInstance(a2, &RetVolume);
  v5 = VolumeFromInstance;
  if ( VolumeFromInstance >= 0 )
  {
    v6 = FltGetVolumeName(RetVolume, &VolumeName, 0);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = CreateFile(v2, a2, &VolumeName, 0x100002u, 0, v12, 1u, 0x4020u, 0, &FileHandle);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v9 = FileHandle;
        v10 = CloseHandle(a2, v8, FileHandle);
        v5 = v10;
        if ( v10 >= 0 )
          v9 = 0;
        else
          WriteLog(0, "WinSetupMon::FlushVolume: CloseHandle failed (0x%08X)", v10);
      }
      else
      {
        WriteLog(0, "WinSetupMon::FlushVolume: CreateFile failed (0x%08X)", v7);
        v9 = FileHandle;
      }
      if ( v9 )
        FltClose(v9);
    }
    else
    {
      WriteLog(0, "WinSetupMon::FlushVolume: FltGetVolumeName failed (0x%08X)", (unsigned int)v6);
    }
  }
  else
  {
    WriteLog(0, "WinSetupMon::FlushVolume: FltGetVolumeFromInstance failed (0x%08X)", (unsigned int)VolumeFromInstance);
  }
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  return v5;
}

```

## disassembly

```asm
0x14000dd90  push    rbp
0x14000dd92  push    rbx
0x14000dd93  push    rsi
0x14000dd94  push    rdi
0x14000dd95  lea     rbp, [rsp-8]
0x14000dd9a  sub     rsp, 108h
0x14000dda1  mov     rax, cs:__security_cookie
0x14000dda8  xor     rax, rsp
0x14000ddab  mov     [rbp+20h+var_30], rax
0x14000ddaf  mov     rdi, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; _FLT_FILTER * FilterHandle
0x14000ddb6  lea     rcx, [rsp+120h+var_B0]; void *
0x14000ddbb  mov     rsi, rdx
0x14000ddbe  mov     [rsp+120h+RetVolume], 0
0x14000ddc7  xor     edx, edx; Val
0x14000ddc9  mov     r8d, 80h; Size
0x14000ddcf  call    memset
0x14000ddd4  lea     rax, [rsp+120h+var_B0]
0x14000ddd9  mov     qword ptr [rsp+120h+VolumeName.Length], 800000h
0x14000dde2  lea     rdx, [rsp+120h+RetVolume]; RetVolume
0x14000dde7  mov     [rsp+120h+VolumeName.Buffer], rax
0x14000ddec  mov     rcx, rsi; Instance
0x14000ddef  mov     [rsp+120h+FileHandle], 0
0x14000ddf8  call    cs:__imp_FltGetVolumeFromInstance
0x14000ddff  nop     dword ptr [rax+rax+00h]
0x14000de04  mov     ebx, eax
0x14000de06  test    eax, eax
0x14000de08  jns     short loc_14000DE20
0x14000de0a  lea     rdx, aWinsetupmonFlu_0; "WinSetupMon::FlushVolume: FltGetVolumeF"...
0x14000de11  mov     r8d, eax
0x14000de14  xor     ecx, ecx
0x14000de16  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000de1b  jmp     loc_14000DEE2
0x14000de20  mov     rcx, [rsp+120h+RetVolume]; Volume
0x14000de25  lea     rdx, [rsp+120h+VolumeName]; VolumeName
0x14000de2a  xor     r8d, r8d; BufferSizeNeeded
0x14000de2d  call    cs:__imp_FltGetVolumeName
0x14000de34  nop     dword ptr [rax+rax+00h]
0x14000de39  mov     ebx, eax
0x14000de3b  test    eax, eax
0x14000de3d  jns     short loc_14000DE48
0x14000de3f  lea     rdx, aWinsetupmonFlu_2; "WinSetupMon::FlushVolume: FltGetVolumeN"...
0x14000de46  jmp     short loc_14000DE11
0x14000de48  lea     rax, [rsp+120h+FileHandle]
0x14000de4d  mov     r9d, 100002h; unsigned int
0x14000de53  mov     [rsp+120h+var_D8], rax; void **
0x14000de58  lea     r8, [rsp+120h+VolumeName]; struct _UNICODE_STRING *
0x14000de5d  mov     [rsp+120h+var_E0], 0; unsigned __int8
0x14000de62  mov     rdx, rsi; Instance
0x14000de65  mov     [rsp+120h+var_E8], 4020h; ULONG
0x14000de6d  mov     rcx, rdi; Filter
0x14000de70  mov     [rsp+120h+var_F0], 1; ULONG
0x14000de78  mov     [rsp+120h+var_100], 0; ULONG
0x14000de80  call    ?CreateFile@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@KKKKKEPEAPEAX@Z; CreateFile(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,ulong,ulong,ulong,ulong,ulong,uchar,void * *)
0x14000de85  mov     ebx, eax
0x14000de87  test    eax, eax
0x14000de89  jns     short loc_14000DEA3
0x14000de8b  mov     r8d, eax
0x14000de8e  lea     rdx, aWinsetupmonFlu; "WinSetupMon::FlushVolume: CreateFile fa"...
0x14000de95  xor     ecx, ecx
0x14000de97  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000de9c  mov     rdi, [rsp+120h+FileHandle]
0x14000dea1  jmp     short loc_14000DECE
0x14000dea3  mov     rdi, [rsp+120h+FileHandle]
0x14000dea8  mov     rcx, rsi; Instance
0x14000deab  mov     r8, rdi; void *
0x14000deae  call    ?CloseHandle@@YAJPEAU_FLT_INSTANCE@@EPEAX@Z; CloseHandle(_FLT_INSTANCE *,uchar,void *)
0x14000deb3  mov     ebx, eax
0x14000deb5  test    eax, eax
0x14000deb7  jns     short loc_14000DECC
0x14000deb9  mov     r8d, eax
0x14000debc  lea     rdx, aWinsetupmonFlu_1; "WinSetupMon::FlushVolume: CloseHandle f"...
0x14000dec3  xor     ecx, ecx
0x14000dec5  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000deca  jmp     short loc_14000DECE
0x14000decc  xor     edi, edi
0x14000dece  test    rdi, rdi
0x14000ded1  jz      short loc_14000DEE2
0x14000ded3  mov     rcx, rdi; FileHandle
0x14000ded6  call    cs:__imp_FltClose
0x14000dedd  nop     dword ptr [rax+rax+00h]
0x14000dee2  mov     rcx, [rsp+120h+RetVolume]; FltObject
0x14000dee7  test    rcx, rcx
0x14000deea  jz      short loc_14000DEF8
0x14000deec  call    cs:__imp_FltObjectDereference
0x14000def3  nop     dword ptr [rax+rax+00h]
0x14000def8  mov     eax, ebx
0x14000defa  mov     rcx, [rbp+20h+var_30]
0x14000defe  xor     rcx, rsp; StackCookie
0x14000df01  call    __security_check_cookie
0x14000df06  add     rsp, 108h
0x14000df0d  pop     rdi
0x14000df0e  pop     rsi
0x14000df0f  pop     rbx
0x14000df10  pop     rbp
0x14000df11  retn
```
