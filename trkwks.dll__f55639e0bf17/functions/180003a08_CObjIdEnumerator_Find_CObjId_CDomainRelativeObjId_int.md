# CObjIdEnumerator::Find(CObjId *,CDomainRelativeObjId *,int)

- ea: `0x180003a08`
- end: `0x180003b49`
- name: `?Find@CObjIdEnumerator@@AEAAHPEAUCObjId@@PEAUCDomainRelativeObjId@@H@Z`
- size: `321`
- prototype: `__int64 __fastcall(CObjIdEnumerator *__hidden this, struct CObjId *, struct CDomainRelativeObjId *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003798`

## callees

- `0x180003a08`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x180003a71`
- `ntdll!NtQueryDirectoryFile` at `0x180003a71`

## pseudocode

```c
__int64 __fastcall CObjIdEnumerator::Find(
        CObjIdEnumerator *this,
        struct CObjId *a2,
        struct CDomainRelativeObjId *a3,
        int a4)
{
  char *FileInformation; // rsi
  _DWORD *v6; // rbx
  unsigned int Information; // eax
  char *v10; // r8
  char *v11; // rcx
  char *v12; // rdx
  __int64 result; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-48h] BYREF

  FileInformation = (char *)this + 24;
  IoStatusBlock = 0;
  v6 = (_DWORD *)((char *)this + 16);
LABEL_2:
  while ( NtQueryDirectoryFile(
            *((HANDLE *)this + 1),
            0,
            0,
            0,
            &IoStatusBlock,
            FileInformation,
            0x900u,
            FileObjectIdInformation,
            0,
            0,
            a4 != 0) >= 0 )
  {
    Information = IoStatusBlock.Information;
    v6 = (_DWORD *)((char *)this + 16);
    if ( !IoStatusBlock.Information )
      break;
    v6 = (_DWORD *)((char *)this + 16);
    *((_DWORD *)this + 4) = IoStatusBlock.Information;
    a4 = 0;
    *((_QWORD *)this + 291) = FileInformation;
    v10 = (char *)this + 64 * (Information / 0x48uLL) + 8 * (Information / 0x48uLL) + 24;
    if ( FileInformation < v10 )
    {
      v11 = FileInformation;
      v12 = FileInformation;
      while ( (*(_QWORD *)v11 & 0xFFFFFFFFFFFFLL) == 3 )
      {
        v11 += 72;
        *((_QWORD *)this + 291) = v11;
        v12 = v11;
        if ( v11 >= v10 )
          goto LABEL_2;
      }
      if ( v12 < v10 )
      {
        result = 1;
        *(_OWORD *)a3 = *(_OWORD *)(v12 + 24);
        *((_OWORD *)a3 + 1) = *(_OWORD *)(v12 + 40);
        *(_OWORD *)a2 = *(_OWORD *)(v12 + 8);
        *((_QWORD *)this + 291) += 72LL;
        return result;
      }
    }
  }
  *v6 = 0;
  return 0;
}

```

## disassembly

```asm
0x180003a08  push    rbx
0x180003a0a  push    rbp
0x180003a0b  push    rsi
0x180003a0c  push    rdi
0x180003a0d  push    r14
0x180003a0f  push    r15
0x180003a11  sub     rsp, 78h
0x180003a15  xorps   xmm0, xmm0
0x180003a18  lea     rsi, [rcx+18h]
0x180003a1c  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180003a21  mov     r14, r8
0x180003a24  lea     rbx, [rcx+10h]
0x180003a28  mov     r15, rdx
0x180003a2b  mov     rdi, rcx
0x180003a2e  mov     rcx, [rdi+8]; FileHandle
0x180003a32  test    r9d, r9d
0x180003a35  setnz   al
0x180003a38  xor     r9d, r9d; ApcContext
0x180003a3b  mov     [rsp+0A8h+RestartScan], al; RestartScan
0x180003a3f  xor     r8d, r8d; ApcRoutine
0x180003a42  mov     [rsp+0A8h+FileName], 0; FileName
0x180003a4b  lea     rax, [rsp+0A8h+var_48]
0x180003a50  mov     [rsp+0A8h+ReturnSingleEntry], 0; ReturnSingleEntry
0x180003a55  xor     edx, edx; Event
0x180003a57  mov     [rsp+0A8h+FileInformationClass], 1Dh; FileInformationClass
0x180003a5f  mov     [rsp+0A8h+Length], 900h; Length
0x180003a67  mov     [rsp+0A8h+FileInformation], rsi; FileInformation
0x180003a6c  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x180003a71  call    cs:__imp_NtQueryDirectoryFile
0x180003a77  test    eax, eax
0x180003a79  js      loc_180003B34
0x180003a7f  mov     rax, [rsp+0A8h+var_48.Information]
0x180003a84  lea     rbx, [rdi+10h]
0x180003a88  test    rax, rax
0x180003a8b  jz      loc_180003B34
0x180003a91  mov     ecx, eax
0x180003a93  lea     rbx, [rdi+10h]
0x180003a97  mov     [rbx], eax
0x180003a99  xor     r9d, r9d
0x180003a9c  mov     rax, 0E38E38E38E38E38Fh
0x180003aa6  mov     [rdi+918h], rsi
0x180003aad  mul     rcx
0x180003ab0  shr     rdx, 6
0x180003ab4  lea     r8, ds:3[rdx*8]
0x180003abc  add     r8, rdx
0x180003abf  lea     r8, [rdi+r8*8]
0x180003ac3  cmp     rsi, r8
0x180003ac6  jnb     loc_180003A2E
0x180003acc  mov     rcx, rsi
0x180003acf  mov     rdx, rsi
0x180003ad2  mov     rax, [rcx]
0x180003ad5  mov     r10, 0FFFFFFFFFFFFh
0x180003adf  and     rax, r10
0x180003ae2  cmp     rax, 3
0x180003ae6  jnz     short loc_180003B00
0x180003ae8  add     rcx, 48h ; 'H'
0x180003aec  mov     [rdi+918h], rcx
0x180003af3  mov     rdx, rcx
0x180003af6  cmp     rcx, r8
0x180003af9  jb      short loc_180003AD2
0x180003afb  jmp     loc_180003A2E
0x180003b00  cmp     rdx, r8
0x180003b03  jnb     loc_180003A2E
0x180003b09  movups  xmm0, xmmword ptr [rdx+18h]
0x180003b0d  mov     eax, 1
0x180003b12  movdqu  xmmword ptr [r14], xmm0
0x180003b17  movups  xmm1, xmmword ptr [rdx+28h]
0x180003b1b  movdqu  xmmword ptr [r14+10h], xmm1
0x180003b21  movups  xmm0, xmmword ptr [rdx+8]
0x180003b25  movdqu  xmmword ptr [r15], xmm0
0x180003b2a  add     qword ptr [rdi+918h], 48h ; 'H'
0x180003b32  jmp     short loc_180003B3C
0x180003b34  mov     dword ptr [rbx], 0
0x180003b3a  xor     eax, eax
0x180003b3c  add     rsp, 78h
0x180003b40  pop     r15
0x180003b42  pop     r14
0x180003b44  pop     rdi
0x180003b45  pop     rsi
0x180003b46  pop     rbp
0x180003b47  pop     rbx
0x180003b48  retn
```
