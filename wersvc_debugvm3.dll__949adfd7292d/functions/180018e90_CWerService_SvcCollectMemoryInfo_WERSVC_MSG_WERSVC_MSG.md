# CWerService::SvcCollectMemoryInfo(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180018e90`
- end: `0x180018ffc`
- name: `?SvcCollectMemoryInfo@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `364`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x18000d640`
- `0x180012600`
- `0x180012e94`
- `0x180018e90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fc0`
- `wer!WerpGetPathOfWERTempDirectory` at `0x180018eda`
- `wer!WerpGetPathOfWERTempDirectory` at `0x180018eda`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::SvcCollectMemoryInfo(CWerService *this, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  __int64 v4; // r14
  signed int PathOfWERTempDirectory; // ebx
  void *v6; // rax
  void *v7; // rsi
  __int64 v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *v10; // rax
  wchar_t v11; // r8
  wchar_t *v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-E0h]
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  void *v16; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v17[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v18[264]; // [rsp+260h] [rbp+160h] BYREF

  *((_WORD *)a2 + 283) = 0;
  v4 = 260;
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v18, 260);
  if ( PathOfWERTempDirectory < 0 )
    goto LABEL_16;
  v15 = 0;
  PathOfWERTempDirectory = UtilGetTempFile(&v15, v18, (__int64)L".csv", v17, v14, 0, 0, 0);
  if ( PathOfWERTempDirectory < 0 )
  {
    v7 = v15;
  }
  else
  {
    v6 = v15;
    v7 = 0;
    v15 = 0;
    v16 = v6;
    PathOfWERTempDirectory = UtilCollectMemoryInfoHandle(&v16);
    if ( PathOfWERTempDirectory < 0 )
    {
      UtilDeleteFilePath(v17);
    }
    else
    {
      v8 = 2147483646;
      v9 = v17;
      v10 = (wchar_t *)((char *)a3 + 48);
      do
      {
        if ( !v8 )
          break;
        v11 = *v9;
        if ( !*v9 )
          break;
        ++v9;
        *v10++ = v11;
        --v8;
        --v4;
      }
      while ( v4 );
      v12 = v10 - 1;
      if ( v4 )
        v12 = v10;
      *v12 = 0;
      PathOfWERTempDirectory = v4 == 0 ? 0x8007007A : 0;
      *((_DWORD *)a3 + 11) = 0;
      *((_DWORD *)a3 + 10) = -268238848;
    }
  }
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  if ( PathOfWERTempDirectory < 0 )
  {
LABEL_16:
    *((_DWORD *)a3 + 10) = -268238847;
    *((_DWORD *)a3 + 11) = PathOfWERTempDirectory;
  }
  return (unsigned int)PathOfWERTempDirectory;
}

```

## disassembly

```asm
0x180018e90  mov     [rsp-8+arg_0], rbx
0x180018e95  push    rbp
0x180018e96  push    rsi
0x180018e97  push    rdi
0x180018e98  push    r14
0x180018e9a  push    r15
0x180018e9c  lea     rbp, [rsp-380h]
0x180018ea4  sub     rsp, 480h
0x180018eab  mov     rax, cs:__security_cookie
0x180018eb2  xor     rax, rsp
0x180018eb5  mov     [rbp+3A0h+var_30], rax
0x180018ebc  mov     rdi, r8
0x180018ebf  xor     r15d, r15d
0x180018ec2  mov     [rdx+236h], r15w
0x180018eca  mov     r14d, 104h
0x180018ed0  mov     edx, r14d
0x180018ed3  lea     rcx, [rbp+3A0h+var_240]
0x180018eda  call    cs:__imp_WerpGetPathOfWERTempDirectory
0x180018ee0  mov     ebx, eax
0x180018ee2  test    eax, eax
0x180018ee4  js      loc_180018FCA
0x180018eea  mov     [rsp+4A0h+var_460], r15
0x180018eef  mov     [rsp+4A0h+var_468], r15d
0x180018ef4  mov     [rsp+4A0h+var_470], r15d
0x180018ef9  mov     [rsp+4A0h+var_478], r15
0x180018efe  lea     r9, [rsp+4A0h+var_450]
0x180018f03  lea     r8, aCsv; ".csv"
0x180018f0a  lea     rdx, [rbp+3A0h+var_240]
0x180018f11  lea     rcx, [rsp+4A0h+var_460]
0x180018f16  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180018f1b  mov     ebx, eax
0x180018f1d  test    eax, eax
0x180018f1f  js      loc_180018FAE
0x180018f25  mov     rax, [rsp+4A0h+var_460]
0x180018f2a  mov     esi, r15d
0x180018f2d  mov     [rsp+4A0h+var_460], r15
0x180018f32  mov     [rsp+4A0h+var_458], rax
0x180018f37  lea     rcx, [rsp+4A0h+var_458]
0x180018f3c  call    ?UtilCollectMemoryInfoHandle@@YAJV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilCollectMemoryInfoHandle(tlx::unique_any<tlx::file_handle_traits>)
0x180018f41  mov     ebx, eax
0x180018f43  test    eax, eax
0x180018f45  js      short loc_180018FA2
0x180018f47  mov     ecx, 7FFFFFFEh
0x180018f4c  lea     rdx, [rsp+4A0h+var_450]
0x180018f51  lea     rax, [rdi+30h]
0x180018f55  test    rcx, rcx
0x180018f58  jz      short loc_180018F79
0x180018f5a  movzx   r8d, word ptr [rdx]
0x180018f5e  test    r8w, r8w
0x180018f62  jz      short loc_180018F79
0x180018f64  add     rdx, 2
0x180018f68  mov     [rax], r8w
0x180018f6c  add     rax, 2
0x180018f70  dec     rcx
0x180018f73  sub     r14, 1
0x180018f77  jnz     short loc_180018F55
0x180018f79  lea     rcx, [rax-2]
0x180018f7d  test    r14, r14
0x180018f80  cmovnz  rcx, rax
0x180018f84  mov     [rcx], r15w
0x180018f88  neg     r14
0x180018f8b  sbb     ebx, ebx
0x180018f8d  not     ebx
0x180018f8f  and     ebx, 8007007Ah
0x180018f95  mov     [rdi+2Ch], r15d
0x180018f99  mov     dword ptr [rdi+28h], 0F0030000h
0x180018fa0  jmp     short loc_180018FB3
0x180018fa2  lea     rcx, [rsp+4A0h+var_450]; wchar_t *
0x180018fa7  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180018fac  jmp     short loc_180018FB3
0x180018fae  mov     rsi, [rsp+4A0h+var_460]
0x180018fb3  lea     rax, [rsi+1]
0x180018fb7  cmp     rax, 1
0x180018fbb  jbe     short loc_180018FC6
0x180018fbd  mov     rcx, rsi; hObject
0x180018fc0  call    cs:__imp_CloseHandle
0x180018fc6  test    ebx, ebx
0x180018fc8  jns     short loc_180018FD4
0x180018fca  mov     dword ptr [rdi+28h], 0F0030001h
0x180018fd1  mov     [rdi+2Ch], ebx
0x180018fd4  mov     eax, ebx
0x180018fd6  mov     rcx, [rbp+3A0h+var_30]
0x180018fdd  xor     rcx, rsp; StackCookie
0x180018fe0  call    __security_check_cookie
0x180018fe5  mov     rbx, [rsp+4A0h+arg_0]
0x180018fed  add     rsp, 480h
0x180018ff4  pop     r15
0x180018ff6  pop     r14
0x180018ff8  pop     rdi
0x180018ff9  pop     rsi
0x180018ffa  pop     rbp
0x180018ffb  retn
```
