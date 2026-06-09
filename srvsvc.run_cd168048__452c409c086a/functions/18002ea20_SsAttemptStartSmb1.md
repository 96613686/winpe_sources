# SsAttemptStartSmb1

- ea: `0x18002ea20`
- end: `0x18002ebf1`
- name: `SsAttemptStartSmb1`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014880`

## callees

- `0x18000b5a0`
- `0x180013924`
- `0x180020dc0`
- `0x180020de8`
- `0x18002ea20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ea2f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ea2f`
- `ntdll!RtlReleaseResource` at `0x18002ebea`
- `ntdll!RtlInitUnicodeString` at `0x18002eafb`
- `ntdll!RtlInitUnicodeString` at `0x18002eb0c`
- `ntdll!RtlInitUnicodeString` at `0x18002eafb`
- `ntdll!RtlInitUnicodeString` at `0x18002eb0c`

## pseudocode

```c
void SsAttemptStartSmb1()
{
  __int64 v0; // rdx
  unsigned int v1; // eax
  _QWORD *v2; // r10
  __int64 v3; // rdx
  struct _UNICODE_STRING *v4; // rax
  struct _UNICODE_STRING *v5; // rbx

  RtlAcquireResourceExclusive(&Resource, 1u);
  if ( Handle )
    goto LABEL_24;
  v1 = SsOpenDeviceEx(L"\\Device\\LanmanServer", v0, &Handle);
  if ( v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v3 = 19;
LABEL_17:
      WPP_SF_d(v2[2], v3, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids, v1);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  v4 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids);
    }
    goto LABEL_18;
  }
  *(_DWORD *)&v4[4].Length = -1;
  RtlInitUnicodeString(v4, &pszDest);
  RtlInitUnicodeString(v5 + 1, &WideCharStr);
  v1 = SsServerFsControl(0x144003u, (__int64)v5, &SsData, 0x1E8u, 0);
  if ( v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v3 = 21;
      goto LABEL_17;
    }
LABEL_18:
    if ( Handle )
    {
      CloseHandle(Handle);
      Handle = 0;
    }
    goto LABEL_24;
  }
  SsServerFsControl(0x144050u, 0, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids);
  }
LABEL_24:
  RtlReleaseResource(&Resource);
}

```

## disassembly

```asm
0x18002ea20  push    rbx
0x18002ea22  sub     rsp, 30h
0x18002ea26  mov     dl, 1; Wait
0x18002ea28  lea     rcx, Resource; Resource
0x18002ea2f  call    cs:__imp_RtlAcquireResourceExclusive
0x18002ea35  cmp     cs:Handle, 0
0x18002ea3d  jnz     loc_18002EBDE
0x18002ea43  lea     r8, Handle
0x18002ea4a  lea     rcx, aDeviceLanmanse; "\\Device\\LanmanServer"
0x18002ea51  call    SsOpenDeviceEx
0x18002ea56  test    eax, eax
0x18002ea58  jz      short loc_18002EA91
0x18002ea5a  mov     r10, cs:WPP_GLOBAL_Control
0x18002ea61  lea     rcx, WPP_GLOBAL_Control
0x18002ea68  cmp     r10, rcx
0x18002ea6b  jz      loc_18002EB71
0x18002ea71  test    byte ptr [r10+1Ch], 8
0x18002ea76  jz      loc_18002EB71
0x18002ea7c  cmp     byte ptr [r10+19h], 1
0x18002ea81  jb      loc_18002EB71
0x18002ea87  mov     edx, 13h
0x18002ea8c  jmp     loc_18002EB5E
0x18002ea91  mov     edx, 60h ; '`'; uBytes
0x18002ea96  lea     ecx, [rdx-20h]; uFlags
0x18002ea99  call    cs:__imp_LocalAlloc
0x18002ea9f  mov     rbx, rax
0x18002eaa2  test    rax, rax
0x18002eaa5  jnz     short loc_18002EAEA
0x18002eaa7  mov     rax, cs:WPP_GLOBAL_Control
0x18002eaae  lea     rcx, WPP_GLOBAL_Control
0x18002eab5  cmp     rax, rcx
0x18002eab8  jz      loc_18002EB71
0x18002eabe  test    byte ptr [rax+1Ch], 8
0x18002eac2  jz      loc_18002EB71
0x18002eac8  cmp     byte ptr [rax+19h], 1
0x18002eacc  jb      loc_18002EB71
0x18002ead2  mov     rcx, [rax+10h]
0x18002ead6  lea     edx, [rbx+14h]
0x18002ead9  lea     r8, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids
0x18002eae0  call    WPP_SF_
0x18002eae5  jmp     loc_18002EB71
0x18002eaea  lea     rdx, pszDest; SourceString
0x18002eaf1  mov     dword ptr [rax+40h], 0FFFFFFFFh
0x18002eaf8  mov     rcx, rbx; DestinationString
0x18002eafb  call    cs:__imp_RtlInitUnicodeString
0x18002eb01  lea     rcx, [rbx+10h]; DestinationString
0x18002eb05  lea     rdx, WideCharStr; SourceString
0x18002eb0c  call    cs:__imp_RtlInitUnicodeString
0x18002eb12  mov     r9d, 1E8h
0x18002eb18  mov     [rsp+38h+var_18], 0; int
0x18002eb20  lea     r8, SsData
0x18002eb27  mov     rdx, rbx
0x18002eb2a  mov     ecx, 144003h; FsControlCode
0x18002eb2f  call    SsServerFsControl
0x18002eb34  test    eax, eax
0x18002eb36  jz      short loc_18002EB90
0x18002eb38  mov     r10, cs:WPP_GLOBAL_Control
0x18002eb3f  lea     rcx, WPP_GLOBAL_Control
0x18002eb46  cmp     r10, rcx
0x18002eb49  jz      short loc_18002EB71
0x18002eb4b  test    byte ptr [r10+1Ch], 8
0x18002eb50  jz      short loc_18002EB71
0x18002eb52  cmp     byte ptr [r10+19h], 1
0x18002eb57  jb      short loc_18002EB71
0x18002eb59  mov     edx, 15h
0x18002eb5e  mov     rcx, [r10+10h]
0x18002eb62  lea     r8, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids
0x18002eb69  mov     r9d, eax
0x18002eb6c  call    WPP_SF_d
0x18002eb71  mov     rcx, cs:Handle; hObject
0x18002eb78  test    rcx, rcx
0x18002eb7b  jz      short loc_18002EBDE
0x18002eb7d  call    cs:__imp_CloseHandle
0x18002eb83  mov     cs:Handle, 0
0x18002eb8e  jmp     short loc_18002EBDE
0x18002eb90  xor     r9d, r9d
0x18002eb93  mov     [rsp+38h+var_18], 0; int
0x18002eb9b  xor     r8d, r8d
0x18002eb9e  xor     edx, edx
0x18002eba0  mov     ecx, 144050h; FsControlCode
0x18002eba5  call    SsServerFsControl
0x18002ebaa  mov     rax, cs:WPP_GLOBAL_Control
0x18002ebb1  lea     rcx, WPP_GLOBAL_Control
0x18002ebb8  cmp     rax, rcx
0x18002ebbb  jz      short loc_18002EBDE
0x18002ebbd  test    byte ptr [rax+1Ch], 8
0x18002ebc1  jz      short loc_18002EBDE
0x18002ebc3  cmp     byte ptr [rax+19h], 2
0x18002ebc7  jb      short loc_18002EBDE
0x18002ebc9  mov     rcx, [rax+10h]
0x18002ebcd  lea     r8, WPP_1fe2c7acda9e304be98aeebb32c32e74_Traceguids
0x18002ebd4  mov     edx, 16h
0x18002ebd9  call    WPP_SF_
0x18002ebde  lea     rcx, Resource
0x18002ebe5  add     rsp, 30h
0x18002ebe9  pop     rbx
0x18002ebea  jmp     cs:__imp_RtlReleaseResource
```
