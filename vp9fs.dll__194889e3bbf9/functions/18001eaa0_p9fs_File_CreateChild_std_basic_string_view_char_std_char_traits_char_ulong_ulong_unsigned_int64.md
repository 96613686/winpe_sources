# p9fs::File::CreateChild(std::basic_string_view<char,std::char_traits<char>>,ulong,ulong,unsigned __int64)

- ea: `0x18001eaa0`
- end: `0x18001ec5d`
- name: `?CreateChild@File@p9fs@@AEAA?AV?$BasicExpected@UQid@p9fs@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@KK_K@Z`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18001fe50`
- `0x18001fea0`

## callees

- `0x180004120`
- `0x18001d940`
- `0x18001e428`
- `0x18001eaa0`
- `0x18001ec64`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec24`
- `lxutil!LxUtilFsFileModeToReparseTag` at `0x18001eb50`
- `lxutil!LxUtilFsFileModeToReparseTag` at `0x18001eb50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::File::CreateChild(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rsi
  __int64 *v11; // r14
  __int64 v12; // r15
  int v13; // eax
  int v14; // eax
  __int128 v17; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v18[8]; // [rsp+80h] [rbp-59h] BYREF
  _DWORD v19[8]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v20[8]; // [rsp+A8h] [rbp-31h] BYREF
  int v21; // [rsp+B0h] [rbp-29h]
  __int128 v22; // [rsp+B8h] [rbp-21h]
  HANDLE hObject; // [rsp+C8h] [rbp-11h]
  __int64 v24; // [rsp+D0h] [rbp-9h] BYREF

  *(_QWORD *)&v17 = a3;
  v8 = *(_QWORD *)(a1 + 72);
  if ( (*(_BYTE *)(v8 + 48) & 1) != 0 )
  {
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -30;
  }
  else if ( *(char *)(v8 + 48) >= 0 )
  {
    v9 = a5 & 0xF000;
    if ( v9 == 0x8000 || v9 == 0x4000 )
    {
      v10 = a6;
      v11 = 0;
      v12 = 0;
    }
    else
    {
      if ( (*(_BYTE *)(v8 + 48) & 4) == 0 || (*(_DWORD *)(v8 + 40) & 0x1000) == 0 )
      {
        *(_BYTE *)a2 = 0;
        *(_DWORD *)(a2 + 8) = -95;
        return a2;
      }
      v10 = a6;
      if ( ((v9 - 0x2000) & 0xFFFFBFFF) != 0 )
        v10 = 0;
      v24 = (unsigned int)LxUtilFsFileModeToReparseTag(a5);
      v11 = &v24;
      v12 = 8;
    }
    v17 = *(_OWORD *)v17;
    p9fs::File::ChildPath(a1, v18, &v17);
    if ( v18[0] )
    {
      *(_QWORD *)&v17 = v12;
      *((_QWORD *)&v17 + 1) = v11;
      p9fs::File::CreateFile(a1, (__int64)v20, (__int64)v19, a4, a5, v10, 128, 2, 0, &v17, 0);
      if ( v20[0] )
      {
        *(_BYTE *)a2 = 1;
        *(_OWORD *)(a2 + 8) = v22;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
      else
      {
        v14 = v21;
        *(_BYTE *)a2 = 0;
        *(_DWORD *)(a2 + 8) = v14;
      }
      if ( v18[0] )
        std::wstring::~wstring(v19);
    }
    else
    {
      v13 = v19[0];
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = v13;
    }
  }
  else
  {
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -13;
  }
  return a2;
}

```

## disassembly

```asm
0x18001eaa0  push    rbp
0x18001eaa2  push    rbx
0x18001eaa3  push    rsi
0x18001eaa4  push    rdi
0x18001eaa5  push    r12
0x18001eaa7  push    r13
0x18001eaa9  push    r14
0x18001eaab  push    r15
0x18001eaad  lea     rbp, [rsp-0Fh]
0x18001eab2  sub     rsp, 0E8h
0x18001eab9  mov     rax, cs:__security_cookie
0x18001eac0  xor     rax, rsp
0x18001eac3  mov     [rbp+47h+var_48], rax
0x18001eac7  mov     [rbp+47h+var_C0], r9d
0x18001eacb  mov     qword ptr [rbp+47h+var_B0], r8
0x18001eacf  mov     rbx, rdx
0x18001ead2  mov     r13, rcx
0x18001ead5  mov     r12d, [rbp+47h+arg_20]
0x18001ead9  mov     rcx, [rcx+48h]
0x18001eadd  test    byte ptr [rcx+30h], 1
0x18001eae1  jz      short loc_18001EAF4
0x18001eae3  xor     edi, edi
0x18001eae5  mov     [rdx], dil
0x18001eae8  mov     dword ptr [rdx+8], 0FFFFFFE2h
0x18001eaef  jmp     loc_18001EC3A
0x18001eaf4  test    byte ptr [rcx+30h], 80h
0x18001eaf8  jz      short loc_18001EB0B
0x18001eafa  xor     edi, edi
0x18001eafc  mov     [rdx], dil
0x18001eaff  mov     dword ptr [rdx+8], 0FFFFFFF3h
0x18001eb06  jmp     loc_18001EC3A
0x18001eb0b  mov     eax, r12d
0x18001eb0e  and     eax, 0F000h
0x18001eb13  cmp     eax, 8000h
0x18001eb18  jz      short loc_18001EB74
0x18001eb1a  cmp     eax, 4000h
0x18001eb1f  jz      short loc_18001EB74
0x18001eb21  test    byte ptr [rcx+30h], 4
0x18001eb25  jz      short loc_18001EB63
0x18001eb27  test    dword ptr [rcx+28h], 1000h
0x18001eb2e  jz      short loc_18001EB63
0x18001eb30  add     eax, 0FFFFE000h
0x18001eb35  test    eax, 0FFFFBFFFh
0x18001eb3a  mov     rsi, [rbp+47h+arg_28]
0x18001eb3e  mov     edi, 0
0x18001eb43  cmovnz  rsi, rdi
0x18001eb47  xor     eax, eax
0x18001eb49  mov     [rbp+47h+var_50], rax
0x18001eb4d  mov     ecx, r12d
0x18001eb50  call    cs:__imp_LxUtilFsFileModeToReparseTag
0x18001eb56  mov     dword ptr [rbp+47h+var_50], eax
0x18001eb59  lea     r14, [rbp+47h+var_50]
0x18001eb5d  lea     r15d, [rdi+8]
0x18001eb61  jmp     short loc_18001EB80
0x18001eb63  xor     edi, edi
0x18001eb65  mov     [rdx], dil
0x18001eb68  mov     dword ptr [rdx+8], 0FFFFFFA1h
0x18001eb6f  jmp     loc_18001EC3A
0x18001eb74  xor     edi, edi
0x18001eb76  mov     rsi, [rbp+47h+arg_28]
0x18001eb7a  mov     r14d, edi
0x18001eb7d  mov     r15d, edi
0x18001eb80  mov     rax, qword ptr [rbp+47h+var_B0]
0x18001eb84  movaps  xmm0, xmmword ptr [rax]
0x18001eb87  movdqa  [rbp+47h+var_B0], xmm0
0x18001eb8c  lea     r8, [rbp+47h+var_B0]
0x18001eb90  lea     rdx, [rbp+47h+var_A0]
0x18001eb94  mov     rcx, r13
0x18001eb97  call    ?ChildPath@File@p9fs@@QEAA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::File::ChildPath(std::string_view)
0x18001eb9c  nop
0x18001eb9d  cmp     [rbp+47h+var_A0], dil
0x18001eba1  jnz     short loc_18001EBB1
0x18001eba3  mov     eax, [rbp+47h+var_98]
0x18001eba6  mov     [rbx], dil
0x18001eba9  mov     [rbx+8], eax
0x18001ebac  jmp     loc_18001EC3A
0x18001ebb1  mov     qword ptr [rbp+47h+var_B0], r15
0x18001ebb5  mov     qword ptr [rbp+47h+var_B0+8], r14
0x18001ebb9  mov     [rsp+120h+var_D0], rdi
0x18001ebbe  lea     rax, [rbp+47h+var_B0]
0x18001ebc2  mov     [rsp+120h+var_D8], rax
0x18001ebc7  mov     [rsp+120h+var_E0], edi
0x18001ebcb  mov     [rsp+120h+var_E8], 2
0x18001ebd3  mov     [rsp+120h+var_F0], 80h
0x18001ebdb  mov     [rsp+120h+var_F8], rsi
0x18001ebe0  mov     [rsp+120h+var_100], r12d
0x18001ebe5  mov     r9d, [rbp+47h+var_C0]
0x18001ebe9  lea     r8, [rbp+47h+var_98]
0x18001ebed  lea     rdx, [rbp+47h+var_78]
0x18001ebf1  mov     rcx, r13
0x18001ebf4  call    ?CreateFile@File@p9fs@@AEAA?AV?$BasicExpected@V?$tuple@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@UQid@p9fs@@K@std@@J@util@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_KKKW4OpenFileFlags@42@V?$span@W4byte@gsl@@$0?0@gsl@@PEAW4OpenFileOutputFlags@42@@Z; p9fs::File::CreateFile(std::wstring const &,ulong,ulong,unsigned __int64,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)
0x18001ebf9  cmp     [rbp+47h+var_78], dil
0x18001ebfd  jnz     short loc_18001EC0A
0x18001ebff  mov     eax, [rbp+47h+var_70]
0x18001ec02  mov     [rbx], dil
0x18001ec05  mov     [rbx+8], eax
0x18001ec08  jmp     short loc_18001EC2B
0x18001ec0a  mov     byte ptr [rbx], 1
0x18001ec0d  movups  xmm0, [rbp+47h+var_68]
0x18001ec11  movdqu  xmmword ptr [rbx+8], xmm0
0x18001ec16  mov     rcx, [rbp+47h+hObject]; hObject
0x18001ec1a  lea     rax, [rcx-1]
0x18001ec1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ec22  ja      short loc_18001EC2B
0x18001ec24  call    cs:__imp_CloseHandle
0x18001ec2a  nop
0x18001ec2b  cmp     [rbp+47h+var_A0], dil
0x18001ec2f  jz      short loc_18001EC3A
0x18001ec31  lea     rcx, [rbp+47h+var_98]
0x18001ec35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ec3a  mov     rax, rbx
0x18001ec3d  mov     rcx, [rbp+47h+var_48]
0x18001ec41  xor     rcx, rsp; StackCookie
0x18001ec44  call    __security_check_cookie
0x18001ec49  add     rsp, 0E8h
0x18001ec50  pop     r15
0x18001ec52  pop     r14
0x18001ec54  pop     r13
0x18001ec56  pop     r12
0x18001ec58  pop     rdi
0x18001ec59  pop     rsi
0x18001ec5a  pop     rbx
0x18001ec5b  pop     rbp
0x18001ec5c  retn
```
