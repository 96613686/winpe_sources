# LuaLookupContext::ReadAt(unsigned __int64,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x1800061c0`
- end: `0x1800062c8`
- name: `?ReadAt@LuaLookupContext@@UEAAJ_K0PEAXPEA_K@Z`
- size: `264`
- prototype: `NTSTATUS __fastcall(HANDLE *this, union _LARGE_INTEGER, unsigned __int64, void *Buffer, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800061c0`
- `0x18001b7b0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180006297`
- `ntdll!NtWaitForSingleObject` at `0x180006297`
- `ntdll!NtReadFile` at `0x18000627f`
- `ntdll!NtReadFile` at `0x18000627f`

## pseudocode

```c
NTSTATUS __fastcall LuaLookupContext::ReadAt(
        HANDLE *this,
        union _LARGE_INTEGER a2,
        unsigned __int64 a3,
        void *Buffer,
        unsigned __int64 *a5)
{
  ULONG Length; // ecx
  NTSTATUS result; // eax
  NTSTATUS Status; // ecx
  int v9; // [rsp+54h] [rbp-2Ch]
  int v10; // [rsp+5Ch] [rbp-24h]
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-18h] BYREF

  ByteOffset = a2;
  Length = 0;
  IoStatusBlock = 0;
  if ( a3 > 0xFFFFFFFF )
  {
    v9 = -1073741675;
    LOBYTE(v10) = -107;
  }
  else
  {
    Length = a3;
    if ( a3 == (unsigned int)a3 )
    {
      v9 = 0;
      LOBYTE(v10) = 0;
    }
    else
    {
      v9 = -1073741595;
      LOBYTE(v10) = -27;
    }
  }
  *(_WORD *)((char *)&v10 + 1) = *(_WORD *)((char *)&v9 + 1);
  HIBYTE(v10) = HIBYTE(v9);
  result = v10;
  if ( v10 >= 0 )
  {
    if ( Length > a3 )
      return -2147483643;
    Status = NtReadFile(this[1], 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
    if ( Status == 259 )
    {
      result = NtWaitForSingleObject(this[1], 0, 0);
      if ( result < 0 )
        return result;
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
      *a5 = IoStatusBlock.Information;
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x1800061c0  push    rbp
0x1800061c2  push    rbx
0x1800061c3  push    rdi
0x1800061c4  mov     rbp, rsp
0x1800061c7  sub     rsp, 80h
0x1800061ce  mov     rax, cs:__security_cookie
0x1800061d5  xor     rax, rsp
0x1800061d8  mov     [rbp+var_8], rax
0x1800061dc  mov     rdi, [rbp+arg_20]
0x1800061e0  xor     eax, eax
0x1800061e2  mov     [rbp+var_2C], eax
0x1800061e5  mov     rbx, rcx
0x1800061e8  mov     eax, 0FFFFFFFFh
0x1800061ed  mov     qword ptr [rbp+var_20], rdx
0x1800061f1  xor     ecx, ecx
0x1800061f3  xorps   xmm0, xmm0
0x1800061f6  movups  xmmword ptr [rbp+var_18], xmm0
0x1800061fa  cmp     r8, rax
0x1800061fd  ja      short loc_180006221
0x1800061ff  mov     ecx, r8d
0x180006202  cmp     r8, rcx
0x180006205  jz      short loc_180006214
0x180006207  mov     [rbp+var_2C], 0C00000E5h
0x18000620e  mov     byte ptr [rbp+var_24], 0E5h
0x180006212  jmp     short loc_18000622C
0x180006214  mov     [rbp+var_2C], 0
0x18000621b  mov     byte ptr [rbp+var_24], 0
0x18000621f  jmp     short loc_18000622C
0x180006221  mov     [rbp+var_2C], 0C0000095h
0x180006228  mov     byte ptr [rbp+var_24], 95h
0x18000622c  movzx   eax, word ptr [rbp+var_2C+1]
0x180006230  mov     word ptr [rbp+var_24+1], ax
0x180006234  mov     al, byte ptr [rbp+var_2C+3]
0x180006237  mov     byte ptr [rbp+var_24+3], al
0x18000623a  mov     eax, [rbp+var_24]
0x18000623d  test    eax, eax
0x18000623f  js      short loc_1800062B1
0x180006241  mov     eax, ecx
0x180006243  cmp     rax, r8
0x180006246  jbe     short loc_18000624F
0x180006248  mov     eax, 80000005h
0x18000624d  jmp     short loc_1800062B1
0x18000624f  mov     [rsp+80h+Key], 0; Key
0x180006258  lea     rax, [rbp+var_20]
0x18000625c  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x180006261  xor     r8d, r8d; ApcRoutine
0x180006264  mov     [rsp+80h+Length], ecx; Length
0x180006268  lea     rax, [rbp+var_18]
0x18000626c  mov     rcx, [rbx+8]; FileHandle
0x180006270  xor     edx, edx; Event
0x180006272  mov     [rsp+80h+Buffer], r9; Buffer
0x180006277  xor     r9d, r9d; ApcContext
0x18000627a  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x18000627f  call    cs:__imp_NtReadFile
0x180006285  mov     ecx, eax
0x180006287  cmp     eax, 103h
0x18000628c  jnz     short loc_1800062A4
0x18000628e  mov     rcx, [rbx+8]; Handle
0x180006292  xor     r8d, r8d; Timeout
0x180006295  xor     edx, edx; Alertable
0x180006297  call    cs:__imp_NtWaitForSingleObject
0x18000629d  test    eax, eax
0x18000629f  js      short loc_1800062B1
0x1800062a1  mov     ecx, dword ptr [rbp+var_18]
0x1800062a4  test    ecx, ecx
0x1800062a6  js      short loc_1800062AF
0x1800062a8  mov     rax, [rbp+var_18.Information]
0x1800062ac  mov     [rdi], rax
0x1800062af  mov     eax, ecx
0x1800062b1  mov     rcx, [rbp+var_8]
0x1800062b5  xor     rcx, rsp; StackCookie
0x1800062b8  call    __security_check_cookie
0x1800062bd  add     rsp, 80h
0x1800062c4  pop     rdi
0x1800062c5  pop     rbx
0x1800062c6  pop     rbp
0x1800062c7  retn
```
