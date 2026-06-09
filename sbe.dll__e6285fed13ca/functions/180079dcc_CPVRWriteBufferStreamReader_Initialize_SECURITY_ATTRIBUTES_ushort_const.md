# CPVRWriteBufferStreamReader::Initialize(_SECURITY_ATTRIBUTES *,ushort const *)

- ea: `0x180079dcc`
- end: `0x180079f8a`
- name: `?Initialize@CPVRWriteBufferStreamReader@@QEAAKPEAU_SECURITY_ATTRIBUTES@@PEBG@Z`
- size: `446`
- prototype: `unsigned int __fastcall(CPVRWriteBufferStreamReader *__hidden this, struct _SECURITY_ATTRIBUTES *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007776c`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x18005f624`
- `0x1800791dc`
- `0x180079d48`
- `0x180079dcc`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180079f38`
- `KERNEL32!CloseHandle` at `0x180079f38`
- `KERNEL32!GetLastError` at `0x180079f14`
- `KERNEL32!GetLastError` at `0x180079f14`
- `KERNEL32!OpenMutexW` at `0x180079f06`
- `KERNEL32!OpenMutexW` at `0x180079f06`

## pseudocode

```c
__int64 __fastcall CPVRWriteBufferStreamReader::Initialize(
        CPVRWriteBufferStreamReader *this,
        struct _SECURITY_ATTRIBUTES *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  DWORD LastError; // ebx
  DWORD v9; // ebp
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  HANDLE v14; // rsi
  WCHAR Name[264]; // [rsp+20h] [rbp-238h] BYREF

  v5 = operator new(0x20u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = &CWin32SharedMem::`vftable';
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 0;
    v5[3] = 0;
    LODWORD(v5) = CWin32SharedMem::Create_((CWin32SharedMem *)v5, a3, 0x70u, 0);
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 5) = v6;
  if ( !v6 )
    goto LABEL_17;
  v7 = v6;
  if ( (int)v5 < 0 )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD *, __int64))*v6)(v7, 1);
    *((_QWORD *)this + 5) = 0;
LABEL_7:
    LastError = 31;
LABEL_18:
    (*(void (__fastcall **)(CPVRWriteBufferStreamReader *))(*(_QWORD *)this + 8LL))(this);
    return LastError;
  }
  v9 = *(_DWORD *)(v6[1] + 20LL);
  (*(void (__fastcall **)(_QWORD *, __int64))*v6)(v6, 1);
  v10 = operator new(0x20u);
  v6 = v10;
  if ( !v10 )
  {
    *((_QWORD *)this + 5) = 0;
LABEL_17:
    LastError = 8;
    goto LABEL_18;
  }
  *v10 = &CWin32SharedMem::`vftable';
  v10[1] = 0;
  *((_DWORD *)v10 + 4) = 0;
  v10[3] = 0;
  v11 = CWin32SharedMem::Create_((CWin32SharedMem *)v10, a3, v9, 0);
  *((_QWORD *)this + 5) = v6;
  if ( v11 < 0 )
  {
    v7 = v6;
    goto LABEL_6;
  }
  if ( (int)CreateWriteCacheLockName(v6[1] + 4LL, v12, v13, Name) < 0 )
    goto LABEL_7;
  v14 = OpenMutexW(0x100000u, 0, Name);
  if ( !v14 )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_18;
  }
  LastError = CPVRWriteBufferStream::Initialize(
                this,
                v14,
                *(struct PVR_WRITE_BUFFER_STREAM **)(*((_QWORD *)this + 5) + 8LL));
  CloseHandle(v14);
  if ( LastError )
    goto LABEL_18;
  return LastError;
}

```

## disassembly

```asm
0x180079dcc  mov     [rsp+arg_8], rbx
0x180079dd1  mov     [rsp+arg_18], rbp
0x180079dd6  push    rsi
0x180079dd7  push    rdi
0x180079dd8  push    r15
0x180079dda  sub     rsp, 240h
0x180079de1  mov     rax, cs:__security_cookie
0x180079de8  xor     rax, rsp
0x180079deb  mov     [rsp+258h+var_28], rax
0x180079df3  mov     rdi, rcx
0x180079df6  mov     rsi, r8
0x180079df9  mov     ecx, 20h ; ' '; Size
0x180079dfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079e03  lea     r15, ??_7CWin32SharedMem@@6B@; const CWin32SharedMem::`vftable'
0x180079e0a  mov     rbx, rax
0x180079e0d  test    rax, rax
0x180079e10  jz      short loc_180079E40
0x180079e12  xor     r9d, r9d; lpFileMappingAttributes
0x180079e15  mov     [rax], r15
0x180079e18  mov     rdx, rsi; lpName
0x180079e1b  mov     qword ptr [rax+8], 0
0x180079e23  mov     rcx, rax; this
0x180079e26  mov     dword ptr [rax+10h], 0
0x180079e2d  mov     qword ptr [rax+18h], 0
0x180079e35  lea     r8d, [r9+70h]; dwMaximumSizeLow
0x180079e39  call    ?Create_@CWin32SharedMem@@AEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z; CWin32SharedMem::Create_(ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x180079e3e  jmp     short loc_180079E42
0x180079e40  xor     ebx, ebx
0x180079e42  mov     [rdi+28h], rbx
0x180079e46  test    rbx, rbx
0x180079e49  jz      loc_180079F4C
0x180079e4f  mov     edx, 1
0x180079e54  mov     rcx, rbx
0x180079e57  test    eax, eax
0x180079e59  jns     short loc_180079E78
0x180079e5b  mov     rax, [rbx]
0x180079e5e  mov     rax, [rax]
0x180079e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e66  mov     qword ptr [rdi+28h], 0
0x180079e6e  mov     ebx, 1Fh
0x180079e73  jmp     loc_180079F51
0x180079e78  mov     rax, [rbx+8]
0x180079e7c  mov     ebp, [rax+14h]
0x180079e7f  mov     rax, [rbx]
0x180079e82  mov     rax, [rax]
0x180079e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e8a  mov     ecx, 20h ; ' '; Size
0x180079e8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079e94  mov     rbx, rax
0x180079e97  test    rax, rax
0x180079e9a  jz      loc_180079F44
0x180079ea0  xor     r9d, r9d; lpFileMappingAttributes
0x180079ea3  mov     [rax], r15
0x180079ea6  mov     r8d, ebp; dwMaximumSizeLow
0x180079ea9  mov     qword ptr [rax+8], 0
0x180079eb1  mov     rdx, rsi; lpName
0x180079eb4  mov     dword ptr [rax+10h], 0
0x180079ebb  mov     rcx, rax; this
0x180079ebe  mov     qword ptr [rax+18h], 0
0x180079ec6  call    ?Create_@CWin32SharedMem@@AEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z; CWin32SharedMem::Create_(ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x180079ecb  mov     [rdi+28h], rbx
0x180079ecf  test    eax, eax
0x180079ed1  jns     short loc_180079EE0
0x180079ed3  mov     edx, 1
0x180079ed8  mov     rcx, rbx
0x180079edb  jmp     loc_180079E5B
0x180079ee0  mov     rcx, [rbx+8]
0x180079ee4  lea     r9, [rsp+258h+Name]
0x180079ee9  add     rcx, 4
0x180079eed  call    CreateWriteCacheLockName
0x180079ef2  test    eax, eax
0x180079ef4  js      loc_180079E6E
0x180079efa  lea     r8, [rsp+258h+Name]; lpName
0x180079eff  xor     edx, edx; bInheritHandle
0x180079f01  mov     ecx, 100000h; dwDesiredAccess
0x180079f06  call    cs:__imp_OpenMutexW
0x180079f0c  mov     rsi, rax
0x180079f0f  test    rax, rax
0x180079f12  jnz     short loc_180079F20
0x180079f14  call    cs:__imp_GetLastError
0x180079f1a  mov     ebx, eax
0x180079f1c  test    eax, eax
0x180079f1e  jnz     short loc_180079F51
0x180079f20  mov     r8, [rdi+28h]
0x180079f24  mov     rdx, rsi; void *
0x180079f27  mov     rcx, rdi; this
0x180079f2a  mov     r8, [r8+8]; struct PVR_WRITE_BUFFER_STREAM *
0x180079f2e  call    ?Initialize@CPVRWriteBufferStream@@IEAAKPEAXPEAUPVR_WRITE_BUFFER_STREAM@@@Z; CPVRWriteBufferStream::Initialize(void *,PVR_WRITE_BUFFER_STREAM *)
0x180079f33  mov     rcx, rsi; hObject
0x180079f36  mov     ebx, eax
0x180079f38  call    cs:__imp_CloseHandle
0x180079f3e  test    ebx, ebx
0x180079f40  jz      short loc_180079F60
0x180079f42  jmp     short loc_180079F51
0x180079f44  mov     qword ptr [rdi+28h], 0
0x180079f4c  mov     ebx, 8
0x180079f51  mov     rdx, [rdi]
0x180079f54  mov     rcx, rdi
0x180079f57  mov     rax, [rdx+8]
0x180079f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f60  mov     eax, ebx
0x180079f62  mov     rcx, [rsp+258h+var_28]
0x180079f6a  xor     rcx, rsp; StackCookie
0x180079f6d  call    __security_check_cookie
0x180079f72  lea     r11, [rsp+258h+var_18]
0x180079f7a  mov     rbx, [r11+28h]
0x180079f7e  mov     rbp, [r11+38h]
0x180079f82  mov     rsp, r11
0x180079f85  pop     r15
0x180079f87  pop     rdi
0x180079f88  pop     rsi
0x180079f89  retn
```
