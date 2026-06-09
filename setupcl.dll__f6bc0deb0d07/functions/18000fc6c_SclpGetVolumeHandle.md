# SclpGetVolumeHandle

- ea: `0x18000fc6c`
- end: `0x18001016a`
- name: `SclpGetVolumeHandle`
- size: `1278`
- prototype: `__int64 __fastcall(__int64, int, __int64, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010170`

## callees

- `0x18000a524`
- `0x18000f7e4`
- `0x18000fab0`
- `0x18000fc6c`

## import_xrefs

- `ntdll!NtClose` at `0x18001004c`
- `ntdll!NtClose` at `0x1800100cd`
- `ntdll!NtClose` at `0x180010147`
- `ntdll!NtClose` at `0x18001004c`
- `ntdll!NtClose` at `0x1800100cd`
- `ntdll!NtClose` at `0x180010147`
- `ntdll!RtlFreeHeap` at `0x1800100b7`
- `ntdll!RtlFreeHeap` at `0x180010117`
- `ntdll!RtlFreeHeap` at `0x180010134`
- `ntdll!RtlFreeHeap` at `0x1800100b7`
- `ntdll!RtlFreeHeap` at `0x180010117`
- `ntdll!RtlFreeHeap` at `0x180010134`
- `ntdll!NtCreateFile` at `0x18000ffe9`
- `ntdll!NtCreateFile` at `0x18000ffe9`
- `ntdll!RtlEqualUnicodeString` at `0x18000ff3f`
- `ntdll!RtlEqualUnicodeString` at `0x18000ff3f`

## string_xrefs

- `0x180010026`: `(%lx): Unable to open handle to [%ws].`

## pseudocode

```c
__int64 __fastcall SclpGetVolumeHandle(__int64 a1, int a2, __int64 a3, void **a4)
{
  PVOID v4; // r14
  int MountPoints; // eax
  _DWORD *v7; // rdi
  int v8; // esi
  __int64 i; // r13
  __int64 v10; // rax
  __int16 v11; // dx
  __int16 v12; // cx
  __int64 v13; // r15
  __int64 v14; // rax
  __int16 v15; // dx
  __int16 v16; // cx
  NTSTATUS v17; // eax
  __int64 v18; // rcx
  int VolumeDiskExtents; // eax
  __int64 j; // rcx
  ULONG ShareAccess[2]; // [rsp+38h] [rbp-89h]
  void *FileHandle; // [rsp+68h] [rbp-59h] BYREF
  PVOID P; // [rsp+70h] [rbp-51h] BYREF
  UNICODE_STRING String1; // [rsp+78h] [rbp-49h] BYREF
  PVOID v26; // [rsp+88h] [rbp-39h] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp+Fh] BYREF

  v4 = 0;
  FileHandle = 0;
  v26 = 0;
  IoStatusBlock = 0;
  P = 0;
  String1 = 0;
  String2 = 0;
  memset(&ObjectAttributes, 0, 44);
  MountPoints = SclpGetMountPoints(a1, (ULONG **)&v26);
  v7 = v26;
  v8 = MountPoints;
  if ( MountPoints >= 0 )
  {
    for ( i = 0; (unsigned int)i < v7[1]; i = (unsigned int)(i + 1) )
    {
      v10 = (unsigned int)v7[6 * i + 2];
      if ( (_DWORD)v10 )
      {
        v11 = v7[6 * i + 3];
        if ( (v11 == 96 || v11 == 98 && *(_WORD *)((char *)v7 + v10 + 96) == 92)
          && *(_WORD *)((char *)v7 + v10) == 92
          && ((v12 = *(_WORD *)((char *)v7 + v10 + 2), v12 == 63) || v12 == 92)
          && *(_WORD *)((char *)v7 + v10 + 4) == 63
          && *(_WORD *)((char *)v7 + v10 + 6) == 92
          && *(_WORD *)((char *)v7 + v10 + 8) == 86
          && *(_WORD *)((char *)v7 + v10 + 10) == 111
          && *(_WORD *)((char *)v7 + v10 + 12) == 108
          && *(_WORD *)((char *)v7 + v10 + 14) == 117
          && *(_WORD *)((char *)v7 + v10 + 16) == 109
          && *(_WORD *)((char *)v7 + v10 + 18) == 101
          && *(_WORD *)((char *)v7 + v10 + 20) == 123
          && *(_WORD *)((char *)v7 + v10 + 38) == 45
          && *(_WORD *)((char *)v7 + v10 + 48) == 45
          && *(_WORD *)((char *)v7 + v10 + 58) == 45
          && *(_WORD *)((char *)v7 + v10 + 68) == 45
          && *(_WORD *)((char *)v7 + v10 + 94) == 125
          && v11 == 96
          && v12 == 63 )
        {
          v13 = (unsigned int)(i + 1);
          String1.Length = v7[6 * i + 7];
          String1.MaximumLength = v7[6 * i + 7];
          String1.Buffer = (PWSTR)((char *)v7 + (unsigned int)v7[6 * i + 6]);
          if ( v8 >= 0 )
          {
            while ( (unsigned int)v13 < v7[1] )
            {
              v14 = (unsigned int)v7[6 * v13 + 2];
              if ( (_DWORD)v14 )
              {
                if ( (v15 = v7[6 * v13 + 3], v15 != 96) && (v15 != 98 || *(_WORD *)((char *)v7 + v14 + 96) != 92)
                  || *(_WORD *)((char *)v7 + v14) != 92
                  || (v16 = *(_WORD *)((char *)v7 + v14 + 2), v16 != 63) && v16 != 92
                  || *(_WORD *)((char *)v7 + v14 + 4) != 63
                  || *(_WORD *)((char *)v7 + v14 + 6) != 92
                  || *(_WORD *)((char *)v7 + v14 + 8) != 86
                  || *(_WORD *)((char *)v7 + v14 + 10) != 111
                  || *(_WORD *)((char *)v7 + v14 + 12) != 108
                  || *(_WORD *)((char *)v7 + v14 + 14) != 117
                  || *(_WORD *)((char *)v7 + v14 + 16) != 109
                  || *(_WORD *)((char *)v7 + v14 + 18) != 101
                  || *(_WORD *)((char *)v7 + v14 + 20) != 123
                  || *(_WORD *)((char *)v7 + v14 + 38) != 45
                  || *(_WORD *)((char *)v7 + v14 + 48) != 45
                  || *(_WORD *)((char *)v7 + v14 + 58) != 45
                  || *(_WORD *)((char *)v7 + v14 + 68) != 45
                  || *(_WORD *)((char *)v7 + v14 + 94) != 125
                  || v15 != 96
                  || v16 != 63
                  || (String2.Length = v7[6 * v13 + 7],
                      String2.MaximumLength = v7[6 * v13 + 7],
                      String2.Buffer = (PWSTR)((char *)v7 + (unsigned int)v7[6 * v13 + 6]),
                      RtlEqualUnicodeString(&String1, &String2, 1u)) )
                {
                  v7[6 * v13 + 2] = 0;
                }
              }
              v13 = (unsigned int)(v13 + 1);
            }
          }
          if ( (unsigned __int64)LOWORD(v7[6 * i + 3]) + 4 > 0x208 )
            goto LABEL_77;
          v7[6 * i + 2] = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &String1;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v17 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
          if ( v17 >= 0 )
          {
            VolumeDiskExtents = SclpGetVolumeDiskExtents(a1, FileHandle, &P);
            v4 = P;
            v8 = VolumeDiskExtents;
            if ( VolumeDiskExtents < 0 )
              goto LABEL_78;
            for ( j = 0; (unsigned int)j < *(_DWORD *)P; j = (unsigned int)(j + 1) )
            {
              if ( *((_DWORD *)P + 6 * j + 2) == a2 && *((_QWORD *)P + 3 * j + 2) == a3 )
              {
                *a4 = FileHandle;
                goto LABEL_78;
              }
            }
            if ( P )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            v4 = 0;
            P = 0;
            if ( FileHandle )
              NtClose(FileHandle);
            FileHandle = 0;
          }
          else
          {
            v18 = a1 + 1152;
            if ( !a1 )
              v18 = 0;
            ShareAccess[0] = v17;
            SclLogGenericMessage(
              v18,
              3,
              (int)SclEvent_Generic_Error,
              800,
              (__int64)"SclpGetVolumeHandle",
              "(%lx): Unable to open handle to [%ws].",
              *(_QWORD *)ShareAccess,
              String1.Buffer);
            if ( FileHandle )
              NtClose(FileHandle);
            FileHandle = 0;
            v8 = 0;
          }
        }
        else
        {
          v7[6 * i + 2] = 0;
        }
      }
    }
    if ( v8 < 0 )
      goto LABEL_78;
LABEL_77:
    v8 = -1073741275;
LABEL_78:
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v8 < 0 && FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fc6c  mov     rax, rsp
0x18000fc6f  mov     [rax+18h], rbx
0x18000fc73  mov     [rax+20h], r9
0x18000fc77  mov     [rax+10h], edx
0x18000fc7a  mov     [rax+8], rcx
0x18000fc7e  push    rbp
0x18000fc7f  push    rsi
0x18000fc80  push    rdi
0x18000fc81  push    r12
0x18000fc83  push    r13
0x18000fc85  push    r14
0x18000fc87  push    r15
0x18000fc89  lea     rbp, [rax-5Fh]
0x18000fc8d  sub     rsp, 0E0h
0x18000fc94  xorps   xmm0, xmm0
0x18000fc97  lea     rdx, [rbp+57h+var_90]
0x18000fc9b  xor     eax, eax
0x18000fc9d  xorps   xmm1, xmm1
0x18000fca0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000fca4  xor     r14d, r14d
0x18000fca7  mov     [rbp+57h+FileHandle], rax
0x18000fcab  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000fcaf  mov     rbx, r8
0x18000fcb2  mov     [rbp+57h+var_90], rax
0x18000fcb6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000fcba  mov     [rbp+57h+P], r14
0x18000fcbe  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x18000fcc2  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x18000fcc6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000fcca  call    SclpGetMountPoints
0x18000fccf  mov     rdi, [rbp+57h+var_90]
0x18000fcd3  mov     esi, eax
0x18000fcd5  test    eax, eax
0x18000fcd7  js      loc_18001011D
0x18000fcdd  xor     r13d, r13d
0x18000fce0  cmp     r13d, [rdi+4]
0x18000fce4  jnb     loc_1800100F7
0x18000fcea  lea     r12, ds:0[r13*2]
0x18000fcf2  add     r12, r13
0x18000fcf5  mov     eax, [rdi+r12*8+8]
0x18000fcfa  test    eax, eax
0x18000fcfc  jz      loc_1800100E2
0x18000fd02  movzx   edx, word ptr [rdi+r12*8+0Ch]
0x18000fd08  cmp     dx, 60h ; '`'
0x18000fd0c  jz      short loc_18000FD24
0x18000fd0e  cmp     dx, 62h ; 'b'
0x18000fd12  jnz     loc_1800100D9
0x18000fd18  cmp     word ptr [rax+rdi+60h], 5Ch ; '\'
0x18000fd1e  jnz     loc_1800100D9
0x18000fd24  cmp     word ptr [rax+rdi], 5Ch ; '\'
0x18000fd29  jnz     loc_1800100D9
0x18000fd2f  movzx   ecx, word ptr [rax+rdi+2]
0x18000fd34  cmp     cx, 3Fh ; '?'
0x18000fd38  jz      short loc_18000FD44
0x18000fd3a  cmp     cx, 5Ch ; '\'
0x18000fd3e  jnz     loc_1800100D9
0x18000fd44  cmp     word ptr [rax+rdi+4], 3Fh ; '?'
0x18000fd4a  jnz     loc_1800100D9
0x18000fd50  cmp     word ptr [rax+rdi+6], 5Ch ; '\'
0x18000fd56  jnz     loc_1800100D9
0x18000fd5c  cmp     word ptr [rax+rdi+8], 56h ; 'V'
0x18000fd62  jnz     loc_1800100D9
0x18000fd68  cmp     word ptr [rax+rdi+0Ah], 6Fh ; 'o'
0x18000fd6e  jnz     loc_1800100D9
0x18000fd74  cmp     word ptr [rax+rdi+0Ch], 6Ch ; 'l'
0x18000fd7a  jnz     loc_1800100D9
0x18000fd80  cmp     word ptr [rax+rdi+0Eh], 75h ; 'u'
0x18000fd86  jnz     loc_1800100D9
0x18000fd8c  cmp     word ptr [rax+rdi+10h], 6Dh ; 'm'
0x18000fd92  jnz     loc_1800100D9
0x18000fd98  cmp     word ptr [rax+rdi+12h], 65h ; 'e'
0x18000fd9e  jnz     loc_1800100D9
0x18000fda4  cmp     word ptr [rax+rdi+14h], 7Bh ; '{'
0x18000fdaa  jnz     loc_1800100D9
0x18000fdb0  cmp     word ptr [rax+rdi+26h], 2Dh ; '-'
0x18000fdb6  jnz     loc_1800100D9
0x18000fdbc  cmp     word ptr [rax+rdi+30h], 2Dh ; '-'
0x18000fdc2  jnz     loc_1800100D9
0x18000fdc8  cmp     word ptr [rax+rdi+3Ah], 2Dh ; '-'
0x18000fdce  jnz     loc_1800100D9
0x18000fdd4  cmp     word ptr [rax+rdi+44h], 2Dh ; '-'
0x18000fdda  jnz     loc_1800100D9
0x18000fde0  cmp     word ptr [rax+rdi+5Eh], 7Dh ; '}'
0x18000fde6  jnz     loc_1800100D9
0x18000fdec  cmp     dx, 60h ; '`'
0x18000fdf0  jnz     loc_1800100D9
0x18000fdf6  cmp     cx, 3Fh ; '?'
0x18000fdfa  jnz     loc_1800100D9
0x18000fe00  movzx   eax, word ptr [rdi+r12*8+1Ch]
0x18000fe06  lea     r15d, [r13+1]
0x18000fe0a  mov     [rbp+57h+String1.Length], ax
0x18000fe0e  movzx   eax, word ptr [rdi+r12*8+1Ch]
0x18000fe14  mov     [rbp+57h+String1.MaximumLength], ax
0x18000fe18  mov     eax, [rdi+r12*8+18h]
0x18000fe1d  add     rax, rdi
0x18000fe20  mov     [rbp+57h+String1.Buffer], rax
0x18000fe24  test    esi, esi
0x18000fe26  js      loc_18000FF59
0x18000fe2c  cmp     r15d, [rdi+4]
0x18000fe30  jnb     loc_18000FF59
0x18000fe36  lea     rsi, [r15+r15*2]
0x18000fe3a  mov     eax, [rdi+rsi*8+8]
0x18000fe3e  test    eax, eax
0x18000fe40  jz      loc_18000FF51
0x18000fe46  movzx   edx, word ptr [rdi+rsi*8+0Ch]
0x18000fe4b  cmp     dx, 60h ; '`'
0x18000fe4f  jz      short loc_18000FE67
0x18000fe51  cmp     dx, 62h ; 'b'
0x18000fe55  jnz     loc_18000FF49
0x18000fe5b  cmp     word ptr [rax+rdi+60h], 5Ch ; '\'
0x18000fe61  jnz     loc_18000FF49
0x18000fe67  cmp     word ptr [rax+rdi], 5Ch ; '\'
0x18000fe6c  jnz     loc_18000FF49
0x18000fe72  movzx   ecx, word ptr [rax+rdi+2]
0x18000fe77  cmp     cx, 3Fh ; '?'
0x18000fe7b  jz      short loc_18000FE87
0x18000fe7d  cmp     cx, 5Ch ; '\'
0x18000fe81  jnz     loc_18000FF49
0x18000fe87  cmp     word ptr [rax+rdi+4], 3Fh ; '?'
0x18000fe8d  jnz     loc_18000FF49
0x18000fe93  cmp     word ptr [rax+rdi+6], 5Ch ; '\'
0x18000fe99  jnz     loc_18000FF49
0x18000fe9f  cmp     word ptr [rax+rdi+8], 56h ; 'V'
0x18000fea5  jnz     loc_18000FF49
0x18000feab  cmp     word ptr [rax+rdi+0Ah], 6Fh ; 'o'
0x18000feb1  jnz     loc_18000FF49
0x18000feb7  cmp     word ptr [rax+rdi+0Ch], 6Ch ; 'l'
0x18000febd  jnz     loc_18000FF49
0x18000fec3  cmp     word ptr [rax+rdi+0Eh], 75h ; 'u'
0x18000fec9  jnz     short loc_18000FF49
0x18000fecb  cmp     word ptr [rax+rdi+10h], 6Dh ; 'm'
0x18000fed1  jnz     short loc_18000FF49
0x18000fed3  cmp     word ptr [rax+rdi+12h], 65h ; 'e'
0x18000fed9  jnz     short loc_18000FF49
0x18000fedb  cmp     word ptr [rax+rdi+14h], 7Bh ; '{'
0x18000fee1  jnz     short loc_18000FF49
0x18000fee3  cmp     word ptr [rax+rdi+26h], 2Dh ; '-'
0x18000fee9  jnz     short loc_18000FF49
0x18000feeb  cmp     word ptr [rax+rdi+30h], 2Dh ; '-'
0x18000fef1  jnz     short loc_18000FF49
0x18000fef3  cmp     word ptr [rax+rdi+3Ah], 2Dh ; '-'
0x18000fef9  jnz     short loc_18000FF49
0x18000fefb  cmp     word ptr [rax+rdi+44h], 2Dh ; '-'
0x18000ff01  jnz     short loc_18000FF49
0x18000ff03  cmp     word ptr [rax+rdi+5Eh], 7Dh ; '}'
0x18000ff09  jnz     short loc_18000FF49
0x18000ff0b  cmp     dx, 60h ; '`'
0x18000ff0f  jnz     short loc_18000FF49
0x18000ff11  cmp     cx, 3Fh ; '?'
0x18000ff15  jnz     short loc_18000FF49
0x18000ff17  movzx   eax, word ptr [rdi+rsi*8+1Ch]
0x18000ff1c  lea     rdx, [rbp+57h+String2]; String2
0x18000ff20  mov     [rbp+57h+String2.Length], ax
0x18000ff24  lea     rcx, [rbp+57h+String1]; String1
0x18000ff28  movzx   eax, word ptr [rdi+rsi*8+1Ch]
0x18000ff2d  mov     r8b, 1; CaseInsensitive
0x18000ff30  mov     [rbp+57h+String2.MaximumLength], ax
0x18000ff34  mov     eax, [rdi+rsi*8+18h]
0x18000ff38  add     rax, rdi
0x18000ff3b  mov     [rbp+57h+String2.Buffer], rax
0x18000ff3f  call    cs:__imp_RtlEqualUnicodeString
0x18000ff45  test    al, al
0x18000ff47  jz      short loc_18000FF51
0x18000ff49  mov     dword ptr [rdi+rsi*8+8], 0
0x18000ff51  inc     r15d
0x18000ff54  jmp     loc_18000FE2C
0x18000ff59  movzx   eax, word ptr [rdi+r12*8+0Ch]
0x18000ff5f  add     rax, 4
0x18000ff63  cmp     rax, 208h
0x18000ff69  ja      loc_1800100FB
0x18000ff6f  mov     dword ptr [rsp+50h], 0; EaLength
0x18000ff77  lea     rax, [rbp+57h+String1]
0x18000ff7b  mov     dword ptr [rdi+r12*8+8], 0
0x18000ff84  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000ff88  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x18000ff91  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000ff95  mov     [rsp+110h+CreateOptions], 0; CreateOptions
0x18000ff9d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000ffa1  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18000ffa9  xorps   xmm0, xmm0
0x18000ffac  mov     [rsp+110h+ShareAccess], 3; ShareAccess
0x18000ffb4  mov     edx, 12019Fh; DesiredAccess
0x18000ffb9  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18000ffc1  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x18000ffca  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000ffd1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000ffd9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ffe0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000ffe4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ffe9  call    cs:__imp_NtCreateFile
0x18000ffef  test    eax, eax
0x18000fff1  jns     short loc_180010061
0x18000fff3  mov     r8, [rbp+57h+arg_0]
0x18000fff7  xor     edx, edx
0x18000fff9  test    r8, r8
0x18000fffc  mov     r9d, 320h
0x180010002  lea     rcx, [r8+480h]
0x180010009  cmovz   rcx, rdx
0x18001000d  lea     r8, SclEvent_Generic_Error
0x180010014  mov     rdx, [rbp+57h+String1.Buffer]
0x180010018  mov     qword ptr [rsp+110h+CreateDisposition], rdx
0x18001001d  mov     edx, 3
0x180010022  mov     [rsp+110h+ShareAccess], eax
0x180010026  lea     rax, aLxUnableToOpen; "(%lx): Unable to open handle to [%ws]."
0x18001002d  mov     qword ptr [rsp+110h+FileAttributes], rax
0x180010032  lea     rax, aSclpgetvolumeh; "SclpGetVolumeHandle"
0x180010039  mov     [rsp+110h+AllocationSize], rax
0x18001003e  call    SclLogGenericMessage
0x180010043  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010047  test    rcx, rcx
0x18001004a  jz      short loc_180010052
0x18001004c  call    cs:__imp_NtClose
0x180010052  mov     [rbp+57h+FileHandle], 0
0x18001005a  xor     esi, esi
0x18001005c  jmp     loc_1800100E2
0x180010061  mov     rdx, [rbp+57h+FileHandle]
0x180010065  lea     r8, [rbp+57h+P]
0x180010069  mov     rcx, [rbp+57h+arg_0]
0x18001006d  call    SclpGetVolumeDiskExtents
0x180010072  mov     r14, [rbp+57h+P]
0x180010076  mov     esi, eax
0x180010078  test    eax, eax
0x18001007a  js      loc_180010100
0x180010080  xor     ecx, ecx
0x180010082  cmp     ecx, [r14]
0x180010085  jnb     short loc_1800100A0
0x180010087  mov     eax, [rbp+57h+arg_8]
0x18001008a  lea     rdx, [rcx+rcx*2]
0x18001008e  cmp     [r14+rdx*8+8], eax
0x180010093  jnz     short loc_18001009C
0x180010095  cmp     [r14+rdx*8+10h], rbx
0x18001009a  jz      short loc_1800100EA
0x18001009c  inc     ecx
0x18001009e  jmp     short loc_180010082
0x1800100a0  test    r14, r14
0x1800100a3  jz      short loc_1800100BD
0x1800100a5  mov     rcx, gs:60h
0x1800100ae  mov     r8, r14; P
0x1800100b1  xor     edx, edx; Flags
0x1800100b3  mov     rcx, [rcx+30h]; HeapHandle
0x1800100b7  call    cs:__imp_RtlFreeHeap
0x1800100bd  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800100c1  xor     r14d, r14d
0x1800100c4  mov     [rbp+57h+P], r14
0x1800100c8  test    rcx, rcx
0x1800100cb  jz      short loc_1800100D3
0x1800100cd  call    cs:__imp_NtClose
0x1800100d3  mov     [rbp+57h+FileHandle], r14
0x1800100d7  jmp     short loc_1800100E2
0x1800100d9  mov     dword ptr [rdi+r12*8+8], 0
0x1800100e2  inc     r13d
0x1800100e5  jmp     loc_18000FCE0
0x1800100ea  mov     rcx, [rbp+57h+arg_18]
0x1800100ee  mov     rax, [rbp+57h+FileHandle]
0x1800100f2  mov     [rcx], rax
0x1800100f5  jmp     short loc_180010100
0x1800100f7  test    esi, esi
0x1800100f9  js      short loc_180010100
0x1800100fb  mov     esi, 0C0000225h
0x180010100  test    r14, r14
0x180010103  jz      short loc_18001011D
0x180010105  mov     rcx, gs:60h
0x18001010e  mov     r8, r14; P
0x180010111  xor     edx, edx; Flags
0x180010113  mov     rcx, [rcx+30h]; HeapHandle
0x180010117  call    cs:__imp_RtlFreeHeap
0x18001011d  test    rdi, rdi
0x180010120  jz      short loc_18001013A
0x180010122  mov     rcx, gs:60h
0x18001012b  mov     r8, rdi; P
0x18001012e  xor     edx, edx; Flags
0x180010130  mov     rcx, [rcx+30h]; HeapHandle
0x180010134  call    cs:__imp_RtlFreeHeap
0x18001013a  test    esi, esi
0x18001013c  jns     short loc_18001014D
0x18001013e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010142  test    rcx, rcx
0x180010145  jz      short loc_18001014D
0x180010147  call    cs:__imp_NtClose
0x18001014d  mov     rbx, [rsp+110h+arg_10]
0x180010155  mov     eax, esi
0x180010157  add     rsp, 0E0h
0x18001015e  pop     r15
0x180010160  pop     r14
0x180010162  pop     r13
0x180010164  pop     r12
0x180010166  pop     rdi
0x180010167  pop     rsi
0x180010168  pop     rbp
0x180010169  retn
```
