# CWerService::SvcCollectSystemInfo(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180019004`
- end: `0x180019170`
- name: `?SvcCollectSystemInfo@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `364`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x18000dd08`
- `0x180012600`
- `0x180012e94`
- `0x180019004`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019134`
- `wer!WerpGetPathOfWERTempDirectory` at `0x18001904e`
- `wer!WerpGetPathOfWERTempDirectory` at `0x18001904e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerService::SvcCollectSystemInfo(CWerService *this, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
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
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v15; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v16[264]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[528]; // [rsp+260h] [rbp+160h] BYREF

  *((_WORD *)a2 + 283) = 0;
  v4 = 260;
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v17, 260);
  if ( PathOfWERTempDirectory < 0 )
    goto LABEL_16;
  v14 = 0;
  PathOfWERTempDirectory = UtilGetTempFile(&v14, v17, L".txt", v16);
  if ( PathOfWERTempDirectory < 0 )
  {
    v7 = v14;
  }
  else
  {
    v6 = v14;
    v7 = 0;
    v14 = 0;
    v15 = v6;
    PathOfWERTempDirectory = UtilCollectSystemInfoHandle(&v15);
    if ( PathOfWERTempDirectory < 0 )
    {
      UtilDeleteFilePath(v16);
    }
    else
    {
      v8 = 2147483646;
      v9 = v16;
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
      *((_DWORD *)a3 + 10) = -268173312;
    }
  }
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  if ( PathOfWERTempDirectory < 0 )
  {
LABEL_16:
    *((_DWORD *)a3 + 10) = -268173311;
    *((_DWORD *)a3 + 11) = PathOfWERTempDirectory;
  }
  return (unsigned int)PathOfWERTempDirectory;
}

```

## disassembly

```asm
0x180019004  mov     [rsp-8+arg_0], rbx
0x180019009  push    rbp
0x18001900a  push    rsi
0x18001900b  push    rdi
0x18001900c  push    r14
0x18001900e  push    r15
0x180019010  lea     rbp, [rsp-380h]
0x180019018  sub     rsp, 480h
0x18001901f  mov     rax, cs:__security_cookie
0x180019026  xor     rax, rsp
0x180019029  mov     [rbp+3A0h+var_30], rax
0x180019030  mov     rdi, r8
0x180019033  xor     r15d, r15d
0x180019036  mov     [rdx+236h], r15w
0x18001903e  mov     r14d, 104h
0x180019044  mov     edx, r14d
0x180019047  lea     rcx, [rbp+3A0h+var_240]
0x18001904e  call    cs:__imp_WerpGetPathOfWERTempDirectory
0x180019054  mov     ebx, eax
0x180019056  test    eax, eax
0x180019058  js      loc_18001913E
0x18001905e  mov     [rsp+4A0h+var_460], r15
0x180019063  mov     [rsp+4A0h+var_468], r15d
0x180019068  mov     [rsp+4A0h+var_470], r15d
0x18001906d  mov     [rsp+4A0h+var_478], r15
0x180019072  lea     r9, [rsp+4A0h+var_450]
0x180019077  lea     r8, aTxt; ".txt"
0x18001907e  lea     rdx, [rbp+3A0h+var_240]
0x180019085  lea     rcx, [rsp+4A0h+var_460]
0x18001908a  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18001908f  mov     ebx, eax
0x180019091  test    eax, eax
0x180019093  js      loc_180019122
0x180019099  mov     rax, [rsp+4A0h+var_460]
0x18001909e  mov     esi, r15d
0x1800190a1  mov     [rsp+4A0h+var_460], r15
0x1800190a6  mov     [rsp+4A0h+var_458], rax
0x1800190ab  lea     rcx, [rsp+4A0h+var_458]
0x1800190b0  call    ?UtilCollectSystemInfoHandle@@YAJV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilCollectSystemInfoHandle(tlx::unique_any<tlx::file_handle_traits>)
0x1800190b5  mov     ebx, eax
0x1800190b7  test    eax, eax
0x1800190b9  js      short loc_180019116
0x1800190bb  mov     ecx, 7FFFFFFEh
0x1800190c0  lea     rdx, [rsp+4A0h+var_450]
0x1800190c5  lea     rax, [rdi+30h]
0x1800190c9  test    rcx, rcx
0x1800190cc  jz      short loc_1800190ED
0x1800190ce  movzx   r8d, word ptr [rdx]
0x1800190d2  test    r8w, r8w
0x1800190d6  jz      short loc_1800190ED
0x1800190d8  add     rdx, 2
0x1800190dc  mov     [rax], r8w
0x1800190e0  add     rax, 2
0x1800190e4  dec     rcx
0x1800190e7  sub     r14, 1
0x1800190eb  jnz     short loc_1800190C9
0x1800190ed  lea     rcx, [rax-2]
0x1800190f1  test    r14, r14
0x1800190f4  cmovnz  rcx, rax
0x1800190f8  mov     [rcx], r15w
0x1800190fc  neg     r14
0x1800190ff  sbb     ebx, ebx
0x180019101  not     ebx
0x180019103  and     ebx, 8007007Ah
0x180019109  mov     [rdi+2Ch], r15d
0x18001910d  mov     dword ptr [rdi+28h], 0F0040000h
0x180019114  jmp     short loc_180019127
0x180019116  lea     rcx, [rsp+4A0h+var_450]; wchar_t *
0x18001911b  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180019120  jmp     short loc_180019127
0x180019122  mov     rsi, [rsp+4A0h+var_460]
0x180019127  lea     rax, [rsi+1]
0x18001912b  cmp     rax, 1
0x18001912f  jbe     short loc_18001913A
0x180019131  mov     rcx, rsi; hObject
0x180019134  call    cs:__imp_CloseHandle
0x18001913a  test    ebx, ebx
0x18001913c  jns     short loc_180019148
0x18001913e  mov     dword ptr [rdi+28h], 0F0040001h
0x180019145  mov     [rdi+2Ch], ebx
0x180019148  mov     eax, ebx
0x18001914a  mov     rcx, [rbp+3A0h+var_30]
0x180019151  xor     rcx, rsp; StackCookie
0x180019154  call    __security_check_cookie
0x180019159  mov     rbx, [rsp+4A0h+arg_0]
0x180019161  add     rsp, 480h
0x180019168  pop     r15
0x18001916a  pop     r14
0x18001916c  pop     rdi
0x18001916d  pop     rsi
0x18001916e  pop     rbp
0x18001916f  retn
```
