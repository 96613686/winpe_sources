# CVolume::FileActionIdNotTunnelled(_FILE_OBJECTID_INFORMATION *)

- ea: `0x180001008`
- end: `0x1800012c2`
- name: `?FileActionIdNotTunnelled@CVolume@@QEAAXPEAU_FILE_OBJECTID_INFORMATION@@@Z`
- size: `698`
- prototype: `void __fastcall(CVolume *__hidden this, struct _FILE_OBJECTID_INFORMATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007a50`

## callees

- `0x180001008`
- `0x1800012c8`
- `0x1800012e8`
- `0x18000131c`
- `0x18000f6bc`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180001120`
- `ntdll!NtCreateFile` at `0x180001195`
- `ntdll!NtCreateFile` at `0x180001120`
- `ntdll!NtCreateFile` at `0x180001195`
- `ntdll!NtFsControlFile` at `0x180001217`
- `ntdll!NtFsControlFile` at `0x180001269`
- `ntdll!NtFsControlFile` at `0x180001217`
- `ntdll!NtFsControlFile` at `0x180001269`
- `ntdll!NtClose` at `0x180001224`
- `ntdll!NtClose` at `0x180001276`
- `ntdll!NtClose` at `0x1800012ba`
- `ntdll!NtClose` at `0x180001224`
- `ntdll!NtClose` at `0x180001276`
- `ntdll!NtClose` at `0x1800012ba`

## pseudocode

```c
void __fastcall CVolume::FileActionIdNotTunnelled(CVolume *this, struct _FILE_OBJECTID_INFORMATION *a2)
{
  void *v4; // rdx
  __m128i v5; // xmm0
  unsigned __int64 v6; // rcx
  NTSTATUS v7; // edi
  NTSTATUS v8; // edi
  void *FileHandle; // [rsp+60h] [rbp-88h] BYREF
  __int128 v10; // [rsp+68h] [rbp-80h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-60h] BYREF
  __m128i v13; // [rsp+C0h] [rbp-28h]

  FileHandle = 0;
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v10 = 0;
    IoStatusBlock = 0;
    v5 = *(__m128i *)((char *)a2 + 40);
    v13 = v5;
    v6 = -v5.m128i_i64[0];
    if ( !v5.m128i_i64[0] )
      v6 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - _mm_srli_si128(v5, 8).m128i_u64[0];
    if ( v6 )
    {
      LODWORD(v10) = 1048592;
      *((_QWORD *)&v10 + 1) = (char *)a2 + 8;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = v4;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v10;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      EnableRestorePrivilege();
      v7 = NtCreateFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x406020u, 0, 0);
      if ( v7 >= 0 )
      {
        v7 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A0u, 0, 0, 0, 0);
        NtClose(FileHandle);
        FileHandle = 0;
      }
      if ( v7 == -1073741808 || (unsigned int)IsErrorDueToLockedVolume(v7) )
        goto LABEL_12;
      LODWORD(v10) = 524296;
      *((_QWORD *)&v10 + 1) = a2;
      v8 = NtCreateFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x406020u, 0, 0);
      if ( v8 >= 0 )
      {
        v8 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x90098u, (char *)a2 + 8, 0x40u, 0, 0);
        NtClose(FileHandle);
        FileHandle = 0;
      }
      if ( v8 == -1073741808 || (unsigned int)IsErrorDueToLockedVolume(v8) )
      {
LABEL_12:
        CVolume::CloseVolumeHandles((__int64)this, 0, 2);
        if ( (*((_BYTE *)g_ptrkwks + 596) & 1) != 0 )
          CNewTimer::SetRecurring((struct CTrkWksSvc *)((char *)g_ptrkwks + 600));
      }
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
}

```

## disassembly

```asm
0x180001008  mov     rax, rsp
0x18000100b  mov     [rax+18h], rbx
0x18000100f  mov     [rax+20h], rsi
0x180001013  push    rdi
0x180001014  push    r14
0x180001016  push    r15
0x180001018  sub     rsp, 0D0h
0x18000101f  mov     r14, rdx
0x180001022  mov     rsi, rcx
0x180001025  xor     ebx, ebx
0x180001027  mov     [rsp+0E8h+FileHandle], rbx
0x18000102c  mov     rdx, [rcx+18h]
0x180001030  test    rdx, rdx
0x180001033  jz      loc_180001295
0x180001039  xorps   xmm0, xmm0
0x18000103c  movups  xmmword ptr [rax-60h], xmm0
0x180001040  movups  xmmword ptr [rax-50h], xmm0
0x180001044  movups  xmmword ptr [rax-40h], xmm0
0x180001048  movups  xmmword ptr [rax-80h], xmm0
0x18000104c  xorps   xmm1, xmm1
0x18000104f  movups  xmmword ptr [rax-70h], xmm1
0x180001053  xorps   xmm2, xmm2
0x180001056  lea     r15, [r14+8]
0x18000105a  movups  xmm0, xmmword ptr [r14+28h]
0x18000105f  movups  xmmword ptr [rax-28h], xmm0
0x180001063  movq    rcx, xmm2
0x180001068  movq    rax, xmm0
0x18000106d  sub     rcx, rax
0x180001070  jnz     short loc_180001089
0x180001072  psrldq  xmm2, 8
0x180001077  movq    rcx, xmm2
0x18000107c  psrldq  xmm0, 8
0x180001081  movq    rax, xmm0
0x180001086  sub     rcx, rax
0x180001089  test    rcx, rcx
0x18000108c  jz      loc_180001295
0x180001092  mov     [rsp+0E8h+var_80], 100010h
0x18000109a  mov     [rsp+0E8h+var_78], r15
0x18000109f  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x1800010aa  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], rdx
0x1800010b2  mov     [rsp+0E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800010bd  lea     rax, [rsp+0E8h+var_80]
0x1800010c2  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x1800010ca  xorps   xmm0, xmm0
0x1800010cd  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800010d6  call    ?EnableRestorePrivilege@@YAXXZ; EnableRestorePrivilege(void)
0x1800010db  mov     [rsp+0E8h+EaLength], ebx; EaLength
0x1800010df  mov     [rsp+0E8h+EaBuffer], rbx; EaBuffer
0x1800010e4  mov     [rsp+0E8h+CreateOptions], 406020h; CreateOptions
0x1800010ec  mov     [rsp+0E8h+CreateDisposition], 1; CreateDisposition
0x1800010f4  mov     [rsp+0E8h+ShareAccess], 7; ShareAccess
0x1800010fc  mov     [rsp+0E8h+FileAttributes], 80h; FileAttributes
0x180001104  mov     [rsp+0E8h+AllocationSize], rbx; AllocationSize
0x180001109  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x18000110e  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x180001116  mov     edx, 100100h; DesiredAccess
0x18000111b  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x180001120  call    cs:__imp_NtCreateFile
0x180001126  mov     edi, eax
0x180001128  test    eax, eax
0x18000112a  jns     loc_1800011E6
0x180001130  cmp     edi, 0C0000010h
0x180001136  jz      short loc_1800011B1
0x180001138  mov     ecx, edi; int
0x18000113a  call    ?IsErrorDueToLockedVolume@@YAHJ@Z; IsErrorDueToLockedVolume(long)
0x18000113f  test    eax, eax
0x180001141  jnz     short loc_1800011B1
0x180001143  mov     [rsp+0E8h+var_80], 80008h
0x18000114b  mov     [rsp+0E8h+var_78], r14
0x180001150  mov     [rsp+0E8h+EaLength], ebx; EaLength
0x180001154  mov     [rsp+0E8h+EaBuffer], rbx; EaBuffer
0x180001159  mov     [rsp+0E8h+CreateOptions], 406020h; CreateOptions
0x180001161  mov     [rsp+0E8h+CreateDisposition], 1; CreateDisposition
0x180001169  mov     [rsp+0E8h+ShareAccess], 7; ShareAccess
0x180001171  mov     [rsp+0E8h+FileAttributes], 80h; FileAttributes
0x180001179  mov     [rsp+0E8h+AllocationSize], rbx; AllocationSize
0x18000117e  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x180001183  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x18000118b  mov     edx, 100100h; DesiredAccess
0x180001190  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x180001195  call    cs:__imp_NtCreateFile
0x18000119b  mov     edi, eax
0x18000119d  test    eax, eax
0x18000119f  jns     loc_180001234
0x1800011a5  cmp     edi, 0C0000010h
0x1800011ab  jnz     loc_180001286
0x1800011b1  mov     r8d, 2
0x1800011b7  xor     edx, edx
0x1800011b9  mov     rcx, rsi
0x1800011bc  call    ?CloseVolumeHandles@CVolume@@QEAAXPEAXW4EHandleChangeReason@1@@Z; CVolume::CloseVolumeHandles(void *,CVolume::EHandleChangeReason)
0x1800011c1  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x1800011c8  test    byte ptr [rcx+254h], 1
0x1800011cf  jz      loc_180001295
0x1800011d5  add     rcx, 258h; this
0x1800011dc  call    ?SetRecurring@CNewTimer@@QEAAXXZ; CNewTimer::SetRecurring(void)
0x1800011e1  jmp     loc_180001295
0x1800011e6  mov     dword ptr [rsp+0E8h+EaBuffer], ebx; OutputBufferLength
0x1800011ea  mov     qword ptr [rsp+0E8h+CreateOptions], rbx; OutputBuffer
0x1800011ef  mov     [rsp+0E8h+CreateDisposition], ebx; InputBufferLength
0x1800011f3  mov     qword ptr [rsp+0E8h+ShareAccess], rbx; InputBuffer
0x1800011f8  mov     [rsp+0E8h+FileAttributes], 900A0h; FsControlCode
0x180001200  lea     rax, [rsp+0E8h+IoStatusBlock]
0x180001205  mov     [rsp+0E8h+AllocationSize], rax; IoStatusBlock
0x18000120a  xor     r9d, r9d; ApcContext
0x18000120d  xor     r8d, r8d; ApcRoutine
0x180001210  xor     edx, edx; Event
0x180001212  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x180001217  call    cs:__imp_NtFsControlFile
0x18000121d  mov     edi, eax
0x18000121f  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x180001224  call    cs:__imp_NtClose
0x18000122a  mov     [rsp+0E8h+FileHandle], rbx
0x18000122f  jmp     loc_180001130
0x180001234  mov     dword ptr [rsp+0E8h+EaBuffer], ebx; OutputBufferLength
0x180001238  mov     qword ptr [rsp+0E8h+CreateOptions], rbx; OutputBuffer
0x18000123d  mov     [rsp+0E8h+CreateDisposition], 40h ; '@'; InputBufferLength
0x180001245  mov     qword ptr [rsp+0E8h+ShareAccess], r15; InputBuffer
0x18000124a  mov     [rsp+0E8h+FileAttributes], 90098h; FsControlCode
0x180001252  lea     rax, [rsp+0E8h+IoStatusBlock]
0x180001257  mov     [rsp+0E8h+AllocationSize], rax; IoStatusBlock
0x18000125c  xor     r9d, r9d; ApcContext
0x18000125f  xor     r8d, r8d; ApcRoutine
0x180001262  xor     edx, edx; Event
0x180001264  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x180001269  call    cs:__imp_NtFsControlFile
0x18000126f  mov     edi, eax
0x180001271  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x180001276  call    cs:__imp_NtClose
0x18000127c  mov     [rsp+0E8h+FileHandle], rbx
0x180001281  jmp     loc_1800011A5
0x180001286  mov     ecx, edi; int
0x180001288  call    ?IsErrorDueToLockedVolume@@YAHJ@Z; IsErrorDueToLockedVolume(long)
0x18000128d  test    eax, eax
0x18000128f  jnz     loc_1800011B1
0x180001295  jmp     short $+2
0x180001297  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x18000129c  test    rcx, rcx
0x18000129f  jnz     short loc_1800012BA
0x1800012a1  lea     r11, [rsp+0E8h+var_18]
0x1800012a9  mov     rbx, [r11+30h]
0x1800012ad  mov     rsi, [r11+38h]
0x1800012b1  mov     rsp, r11
0x1800012b4  pop     r15
0x1800012b6  pop     r14
0x1800012b8  pop     rdi
0x1800012b9  retn
0x1800012ba  call    cs:__imp_NtClose
0x1800012c0  jmp     short loc_1800012A1
0x1800110b0  push    rbp
0x1800110b2  sub     rsp, 60h
0x1800110b6  mov     rbp, rdx
0x1800110b9  mov     eax, 1
0x1800110be  add     rsp, 60h
0x1800110c2  pop     rbp
0x1800110c3  retn
```
