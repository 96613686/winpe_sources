# CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::CreateAttributeFilename(ushort * *)

- ea: `0x18006ab50`
- end: `0x18006acdd`
- name: `?CreateAttributeFilename@ASF_MULTI_FILE_RECORDER_NODE@CDVRRingBufferWriter@@QEAAJPEAPEAG@Z`
- size: `397`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18006ace4`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000262c`
- `0x18006ab50`
- `0x180074ec4`
- `0x180076948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006ac44`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006ac44`
- `KERNEL32!GetLastError` at `0x18006abe3`
- `KERNEL32!GetLastError` at `0x18006abe3`
- `KERNEL32!GetFullPathNameW` at `0x18006abd6`
- `KERNEL32!GetFullPathNameW` at `0x18006ac2d`
- `KERNEL32!GetFullPathNameW` at `0x18006abd6`
- `KERNEL32!GetFullPathNameW` at `0x18006ac2d`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::CreateAttributeFilename(
        CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *this,
        unsigned __int16 **a2)
{
  wchar_t *v4; // rbx
  int v5; // esi
  unsigned __int64 v6; // rdx
  DWORD FullPathNameW; // eax
  DWORD v8; // r15d
  unsigned __int64 v9; // rdi
  WCHAR *v10; // rax
  DWORD v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rcx
  size_t v14; // rdi
  unsigned int v16; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+34h] [rbp-54h]
  WCHAR *v18; // [rsp+38h] [rbp-50h]
  CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *v19; // [rsp+40h] [rbp-48h]
  LPWSTR FilePart; // [rsp+48h] [rbp-40h] BYREF
  WCHAR Buffer; // [rsp+50h] [rbp-38h] BYREF

  v19 = this;
  v4 = 0;
  v18 = 0;
  v5 = 1;
  v17 = 1;
  v16 = 0;
  if ( (int)CDVRFileCollection::Lock(*((_QWORD *)this + 1), (char *)this + 32, &v16, 29, 0) >= 0 )
  {
    Buffer = 0;
    FilePart = 0;
    FullPathNameW = GetFullPathNameW(*(LPCWSTR *)(*((_QWORD *)this + 2) + 56LL), 0, &Buffer, 0);
    v8 = FullPathNameW;
    if ( !FullPathNameW )
    {
LABEL_3:
      GetLastError();
      goto LABEL_14;
    }
    v9 = FullPathNameW + 10;
    v10 = (WCHAR *)operator new[](saturated_mul(v9, 2u));
    v4 = v10;
    v18 = v10;
    if ( v10 )
    {
      v11 = GetFullPathNameW(*(LPCWSTR *)(*((_QWORD *)this + 2) + 56LL), v8 + 1, v10, &FilePart);
      if ( !v11 )
        goto LABEL_3;
      if ( v11 <= v8 )
      {
        v12 = wcsrchr(v4, 0x2Eu);
        v13 = v12;
        if ( v12 && v12 >= FilePart )
        {
          v14 = v9 - (v12 - v4);
        }
        else
        {
          v14 = -1;
          do
            ++v14;
          while ( v4[v14] );
          v13 = &v4[v14];
        }
        swprintf_s(v13, v14, L"_attr.sbe");
        *a2 = v4;
        v5 = 0;
        v17 = 0;
      }
    }
  }
LABEL_14:
  if ( v5 )
    operator delete(v4, v6);
  return CDVRFileCollection::Unlock(*((_QWORD *)this + 1), v6, v16, 29, 0);
}

```

## disassembly

```asm
0x18006ab50  mov     r11, rsp
0x18006ab53  mov     [r11+18h], rbx
0x18006ab57  mov     [r11+20h], rsi
0x18006ab5b  push    rdi
0x18006ab5c  push    r12
0x18006ab5e  push    r13
0x18006ab60  push    r14
0x18006ab62  push    r15
0x18006ab64  sub     rsp, 60h
0x18006ab68  mov     rax, cs:__security_cookie
0x18006ab6f  xor     rax, rsp
0x18006ab72  mov     [rsp+88h+var_30], rax
0x18006ab77  mov     r12, rdx
0x18006ab7a  mov     r14, rcx
0x18006ab7d  mov     [rsp+88h+var_48], rcx
0x18006ab82  xor     r13d, r13d
0x18006ab85  mov     ebx, r13d
0x18006ab88  mov     [r11-50h], rbx
0x18006ab8c  lea     esi, [r13+1]
0x18006ab90  mov     [rsp+88h+var_54], esi
0x18006ab94  mov     [r11-58h], r13d
0x18006ab98  lea     rdx, [rcx+20h]
0x18006ab9c  mov     [r11-68h], r13d
0x18006aba0  lea     r9d, [r13+1Dh]
0x18006aba4  lea     r8, [r11-58h]
0x18006aba8  mov     rcx, [rcx+8]
0x18006abac  call    ?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)
0x18006abb1  test    eax, eax
0x18006abb3  js      loc_18006AC91
0x18006abb9  mov     [rsp+88h+Buffer], r13w
0x18006abbf  mov     [rsp+88h+FilePart], r13
0x18006abc4  mov     rcx, [r14+10h]
0x18006abc8  xor     r9d, r9d; lpFilePart
0x18006abcb  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x18006abd0  xor     edx, edx; nBufferLength
0x18006abd2  mov     rcx, [rcx+38h]; lpFileName
0x18006abd6  call    cs:__imp_GetFullPathNameW
0x18006abdc  mov     r15d, eax
0x18006abdf  test    eax, eax
0x18006abe1  jnz     short loc_18006ABEE
0x18006abe3  call    cs:__imp_GetLastError
0x18006abe9  jmp     loc_18006AC91
0x18006abee  lea     edi, [rax+0Ah]
0x18006abf1  mov     eax, 2
0x18006abf6  mul     rdi
0x18006abf9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006ac00  cmovb   rax, rcx
0x18006ac04  mov     rcx, rax; unsigned __int64
0x18006ac07  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006ac0c  mov     rbx, rax
0x18006ac0f  mov     [rsp+88h+var_50], rax
0x18006ac14  test    rax, rax
0x18006ac17  jz      short loc_18006AC91
0x18006ac19  lea     edx, [r15+1]; nBufferLength
0x18006ac1d  mov     rcx, [r14+10h]
0x18006ac21  lea     r9, [rsp+88h+FilePart]; lpFilePart
0x18006ac26  mov     r8, rax; lpBuffer
0x18006ac29  mov     rcx, [rcx+38h]; lpFileName
0x18006ac2d  call    cs:__imp_GetFullPathNameW
0x18006ac33  test    eax, eax
0x18006ac35  jz      short loc_18006ABE3
0x18006ac37  cmp     eax, r15d
0x18006ac3a  ja      short loc_18006AC91
0x18006ac3c  mov     edx, 2Eh ; '.'; Ch
0x18006ac41  mov     rcx, rbx; Str
0x18006ac44  call    cs:__imp_wcsrchr
0x18006ac4a  mov     rcx, rax
0x18006ac4d  test    rax, rax
0x18006ac50  jz      short loc_18006AC64
0x18006ac52  cmp     rax, [rsp+88h+FilePart]
0x18006ac57  jb      short loc_18006AC64
0x18006ac59  sub     rax, rbx
0x18006ac5c  sar     rax, 1
0x18006ac5f  sub     rdi, rax
0x18006ac62  jmp     short loc_18006AC76
0x18006ac64  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006ac68  inc     rdi
0x18006ac6b  cmp     [rbx+rdi*2], r13w
0x18006ac70  jnz     short loc_18006AC68
0x18006ac72  lea     rcx, [rbx+rdi*2]; Buffer
0x18006ac76  lea     r8, aAttrSbe; "_attr.sbe"
0x18006ac7d  mov     rdx, rdi; BufferCount
0x18006ac80  call    swprintf_s
0x18006ac85  mov     [r12], rbx
0x18006ac89  mov     esi, r13d
0x18006ac8c  mov     [rsp+88h+var_54], r13d
0x18006ac91  test    esi, esi
0x18006ac93  jz      short loc_18006AC9D
0x18006ac95  mov     rcx, rbx; void *
0x18006ac98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ac9d  mov     [rsp+88h+var_68], r13d
0x18006aca2  mov     r9d, 1Dh
0x18006aca8  mov     r8d, [rsp+88h+var_58]
0x18006acad  mov     rcx, [r14+8]
0x18006acb1  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x18006acb6  mov     rcx, [rsp+88h+var_30]
0x18006acbb  xor     rcx, rsp; StackCookie
0x18006acbe  call    __security_check_cookie
0x18006acc3  lea     r11, [rsp+88h+var_28]
0x18006acc8  mov     rbx, [r11+40h]
0x18006accc  mov     rsi, [r11+48h]
0x18006acd0  mov     rsp, r11
0x18006acd3  pop     r15
0x18006acd5  pop     r14
0x18006acd7  pop     r13
0x18006acd9  pop     r12
0x18006acdb  pop     rdi
0x18006acdc  retn
0x1800b4088  push    rbp
0x1800b408a  sub     rsp, 30h
0x1800b408e  mov     rbp, rdx
0x1800b4091  cmp     dword ptr [rbp+34h], 0
0x1800b4095  jz      short loc_1800B40A1
0x1800b4097  mov     rcx, [rbp+38h]; void *
0x1800b409b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b40a0  nop
0x1800b40a1  mov     [rsp+38h+var_18], 0
0x1800b40a9  mov     r9d, 1Dh
0x1800b40af  mov     r8d, [rbp+30h]
0x1800b40b3  mov     rcx, [rbp+40h]
0x1800b40b7  mov     rcx, [rcx+8]
0x1800b40bb  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x1800b40c0  nop
0x1800b40c1  add     rsp, 30h
0x1800b40c5  pop     rbp
0x1800b40c6  retn
```
