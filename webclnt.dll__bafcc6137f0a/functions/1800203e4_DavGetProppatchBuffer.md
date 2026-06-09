# DavGetProppatchBuffer

- ea: `0x1800203e4`
- end: `0x1800206b4`
- name: `DavGetProppatchBuffer`
- size: `720`
- prototype: `DWORD __fastcall(int, int, int, int, FILETIME *lpFileTime, FILETIME *, FILETIME *, int, char *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f190`
- `0x18002097c`
- `0x180024190`

## callees

- `0x18000b7b4`
- `0x180014cb4`
- `0x18001f058`
- `0x1800203e4`
- `0x18002cf62`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020547`

## string_xrefs

- `0x180020579`: `<Z:Win32LastAccessTime>`
- `0x180020569`: `</Z:Win32LastAccessTime>`

## pseudocode

```c
DWORD __fastcall DavGetProppatchBuffer(
        int a1,
        int a2,
        int a3,
        int a4,
        FILETIME *lpFileTime,
        FILETIME *a6,
        FILETIME *a7,
        int a8,
        char *a9,
        unsigned int *a10)
{
  unsigned int *v10; // rdi
  unsigned int v15; // eax
  char *v17; // rbx
  unsigned int v18; // eax
  char *v19; // rbx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // r9d
  __int64 v23; // [rsp+70h] [rbp+30h] BYREF

  v10 = a10;
  v15 = (a2 != 0 ? 0xAD : 0) + (a1 != 0 ? 0xA9 : 0) + (a4 != 0 ? 227 : 170) + (a3 != 0 ? 0xB1 : 0);
  if ( v15 > *a10 )
  {
    *a10 = v15;
    return 122;
  }
  v17 = a9;
  memset_0(a9, 0, *a10);
  v18 = *v10;
  qmemcpy(
    v17,
    "<?xml version=\"1.0\" encoding=\"utf-8\" ?><D:propertyupdate xmlns:D=\"DAV:\" xmlns:Z=\"urn:schemas-microsoft-com:\""
    "><D:set><D:prop>",
    124);
  LODWORD(v23) = v18 - 124;
  v19 = v17 + 124;
  a10 = (unsigned int *)v19;
  if ( a1 )
  {
    if ( !(unsigned int)DavConvertTimeToXml(
                          rgCreationTimeTagHeader,
                          0x15u,
                          rgCreationTimeTagTrailer,
                          0x16u,
                          lpFileTime,
                          (void **)&a10,
                          &v23) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return GetLastError();
      v21 = 56;
LABEL_8:
      WPP_SF_(v20[2], v21, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
      return GetLastError();
    }
    v19 = (char *)a10;
  }
  if ( a2 )
  {
    if ( !(unsigned int)DavConvertTimeToXml(
                          rgLastAccessTimeTagHeader,
                          0x17u,
                          rgLastAccessTimeTagTrailer,
                          0x18u,
                          a6,
                          (void **)&a10,
                          &v23) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return GetLastError();
      v21 = 57;
      goto LABEL_8;
    }
    v19 = (char *)a10;
  }
  if ( a3 )
  {
    if ( !(unsigned int)DavConvertTimeToXml(
                          rgLastModifiedTimeTagHeader,
                          0x19u,
                          rgLastModifiedTimeTagTrailer,
                          0x1Au,
                          a7,
                          (void **)&a10,
                          &v23) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return GetLastError();
      v21 = 58;
      goto LABEL_8;
    }
    v19 = (char *)a10;
  }
  if ( a4 )
  {
    v22 = a8;
    qmemcpy(v19, "<Z:Win32FileAttributes>", 23);
    StringCbPrintfA(v19 + 23, 0x12u, "%8.8x", v22);
    qmemcpy(v19 + 31, "</Z:Win32FileAttributes>", 24);
    v19 += 55;
  }
  qmemcpy(v19, "</D:prop></D:set></D:propertyupdate>", 36);
  return 0;
}

```

## disassembly

```asm
0x1800203e4  mov     [rsp-28h+arg_8], rbx
0x1800203e9  mov     [rsp-28h+arg_10], rsi
0x1800203ee  push    rbp
0x1800203ef  push    rdi
0x1800203f0  push    r12
0x1800203f2  push    r14
0x1800203f4  push    r15
0x1800203f6  mov     rbp, rsp
0x1800203f9  sub     rsp, 40h
0x1800203fd  mov     rdi, [rbp+arg_48]
0x180020401  mov     r12d, ecx
0x180020404  mov     eax, r9d
0x180020407  mov     r15d, r9d
0x18002040a  neg     eax
0x18002040c  mov     r14d, r8d
0x18002040f  mov     eax, ecx
0x180020411  mov     esi, edx
0x180020413  sbb     r11d, r11d
0x180020416  and     r11d, 39h
0x18002041a  add     r11d, 0AAh
0x180020421  neg     eax
0x180020423  mov     eax, edx
0x180020425  sbb     r10d, r10d
0x180020428  and     r10d, 0A9h
0x18002042f  add     r11d, r10d
0x180020432  neg     eax
0x180020434  mov     eax, r8d
0x180020437  sbb     ecx, ecx
0x180020439  and     ecx, 0ADh
0x18002043f  add     r11d, ecx
0x180020442  neg     eax
0x180020444  sbb     ecx, ecx
0x180020446  and     ecx, 0B1h
0x18002044c  lea     eax, [r11+rcx]
0x180020450  cmp     eax, [rdi]
0x180020452  jbe     short loc_180020460
0x180020454  mov     [rdi], eax
0x180020456  mov     eax, 7Ah ; 'z'
0x18002045b  jmp     loc_18002069B
0x180020460  mov     rbx, [rbp+arg_40]
0x180020464  xor     edx, edx; Val
0x180020466  mov     r8d, [rdi]; Size
0x180020469  mov     rcx, rbx; void *
0x18002046c  call    memset_0
0x180020471  movaps  xmm0, cs:rgPropPatchHeader
0x180020478  mov     eax, [rdi]
0x18002047a  movups  xmmword ptr [rbx], xmm0
0x18002047d  add     eax, 0FFFFFF84h
0x180020480  movaps  xmm1, cs:xmmword_1800365B0
0x180020487  movups  xmmword ptr [rbx+10h], xmm1
0x18002048b  mov     dword ptr [rbp+arg_0], eax
0x18002048e  movaps  xmm0, cs:xmmword_1800365C0
0x180020495  movups  xmmword ptr [rbx+20h], xmm0
0x180020499  movaps  xmm1, cs:xmmword_1800365D0
0x1800204a0  movups  xmmword ptr [rbx+30h], xmm1
0x1800204a4  movaps  xmm0, cs:xmmword_1800365E0
0x1800204ab  movups  xmmword ptr [rbx+40h], xmm0
0x1800204af  movaps  xmm1, cs:xmmword_1800365F0
0x1800204b6  movups  xmmword ptr [rbx+50h], xmm1
0x1800204ba  movaps  xmm0, cs:xmmword_180036600
0x1800204c1  movups  xmmword ptr [rbx+60h], xmm0
0x1800204c5  movups  xmm1, cs:xmmword_180036600+0Ch
0x1800204cc  movups  xmmword ptr [rbx+6Ch], xmm1
0x1800204d0  add     rbx, 7Ch ; '|'
0x1800204d4  mov     [rbp+arg_48], rbx
0x1800204d8  test    r12d, r12d
0x1800204db  jz      short loc_180020556
0x1800204dd  lea     rax, [rbp+arg_0]
0x1800204e1  mov     r9d, 16h
0x1800204e7  mov     [rsp+40h+var_10], rax; __int64
0x1800204ec  lea     r8, rgCreationTimeTagTrailer; "</Z:Win32CreationTime>"
0x1800204f3  lea     rax, [rbp+arg_48]
0x1800204f7  mov     [rsp+40h+var_18], rax; __int64
0x1800204fc  lea     rcx, rgCreationTimeTagHeader; "<Z:Win32CreationTime>"
0x180020503  mov     rax, [rbp+arg_20]
0x180020507  lea     edx, [r9-1]; Size
0x18002050b  mov     [rsp+40h+lpFileTime], rax; lpFileTime
0x180020510  call    DavConvertTimeToXml
0x180020515  test    eax, eax
0x180020517  jnz     short loc_180020552
0x180020519  mov     rcx, cs:WPP_GLOBAL_Control
0x180020520  lea     rax, WPP_GLOBAL_Control
0x180020527  cmp     rcx, rax
0x18002052a  jz      short loc_180020547
0x18002052c  test    byte ptr [rcx+1Ch], 1
0x180020530  jz      short loc_180020547
0x180020532  mov     edx, 38h ; '8'
0x180020537  mov     rcx, [rcx+10h]
0x18002053b  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x180020542  call    WPP_SF_
0x180020547  call    cs:__imp_GetLastError
0x18002054d  jmp     loc_18002069B
0x180020552  mov     rbx, [rbp+arg_48]
0x180020556  test    esi, esi
0x180020558  jz      short loc_1800205BA
0x18002055a  lea     rax, [rbp+arg_0]
0x18002055e  mov     r9d, 18h
0x180020564  mov     [rsp+40h+var_10], rax; __int64
0x180020569  lea     r8, rgLastAccessTimeTagTrailer; "</Z:Win32LastAccessTime>"
0x180020570  lea     rax, [rbp+arg_48]
0x180020574  mov     [rsp+40h+var_18], rax; __int64
0x180020579  lea     rcx, rgLastAccessTimeTagHeader; "<Z:Win32LastAccessTime>"
0x180020580  mov     rax, [rbp+arg_28]
0x180020584  lea     edx, [r9-1]; Size
0x180020588  mov     [rsp+40h+lpFileTime], rax; lpFileTime
0x18002058d  call    DavConvertTimeToXml
0x180020592  test    eax, eax
0x180020594  jnz     short loc_1800205B6
0x180020596  mov     rcx, cs:WPP_GLOBAL_Control
0x18002059d  lea     rax, WPP_GLOBAL_Control
0x1800205a4  cmp     rcx, rax
0x1800205a7  jz      short loc_180020547
0x1800205a9  test    byte ptr [rcx+1Ch], 1
0x1800205ad  jz      short loc_180020547
0x1800205af  mov     edx, 39h ; '9'
0x1800205b4  jmp     short loc_180020537
0x1800205b6  mov     rbx, [rbp+arg_48]
0x1800205ba  test    r14d, r14d
0x1800205bd  jz      short loc_18002062A
0x1800205bf  lea     rax, [rbp+arg_0]
0x1800205c3  mov     r9d, 1Ah
0x1800205c9  mov     [rsp+40h+var_10], rax; __int64
0x1800205ce  lea     r8, rgLastModifiedTimeTagTrailer; "</Z:Win32LastModifiedTime>"
0x1800205d5  lea     rax, [rbp+arg_48]
0x1800205d9  mov     [rsp+40h+var_18], rax; __int64
0x1800205de  lea     rcx, rgLastModifiedTimeTagHeader; "<Z:Win32LastModifiedTime>"
0x1800205e5  mov     rax, [rbp+arg_30]
0x1800205e9  lea     edx, [r9-1]; Size
0x1800205ed  mov     [rsp+40h+lpFileTime], rax; lpFileTime
0x1800205f2  call    DavConvertTimeToXml
0x1800205f7  test    eax, eax
0x1800205f9  jnz     short loc_180020626
0x1800205fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180020602  lea     rax, WPP_GLOBAL_Control
0x180020609  cmp     rcx, rax
0x18002060c  jz      loc_180020547
0x180020612  test    byte ptr [rcx+1Ch], 1
0x180020616  jz      loc_180020547
0x18002061c  mov     edx, 3Ah ; ':'
0x180020621  jmp     loc_180020537
0x180020626  mov     rbx, [rbp+arg_48]
0x18002062a  test    r15d, r15d
0x18002062d  jz      short loc_18002067B
0x18002062f  movups  xmm0, cs:rgFileAttributesTagHeader
0x180020636  mov     r9d, [rbp+arg_38]
0x18002063a  lea     r8, a88x; "%8.8x"
0x180020641  mov     edx, 12h; cbDest
0x180020646  lea     rcx, [rbx+17h]; pszDest
0x18002064a  movups  xmmword ptr [rbx], xmm0
0x18002064d  movsd   xmm1, qword ptr cs:rgFileAttributesTagHeader+0Fh
0x180020655  movsd   qword ptr [rbx+0Fh], xmm1
0x18002065a  call    StringCbPrintfA
0x18002065f  movups  xmm0, cs:rgFileAttributesTagTrailer
0x180020666  movups  xmmword ptr [rbx+1Fh], xmm0
0x18002066a  movsd   xmm1, cs:qword_180036588
0x180020672  movsd   qword ptr [rbx+2Fh], xmm1
0x180020677  add     rbx, 37h ; '7'
0x18002067b  movups  xmm0, cs:rgPropPatchTrailer
0x180020682  movups  xmmword ptr [rbx], xmm0
0x180020685  movups  xmm1, cs:xmmword_180036560
0x18002068c  movups  xmmword ptr [rbx+10h], xmm1
0x180020690  mov     eax, cs:dword_180036570
0x180020696  mov     [rbx+20h], eax
0x180020699  xor     eax, eax
0x18002069b  lea     r11, [rsp+40h+var_s0]
0x1800206a0  mov     rbx, [r11+38h]
0x1800206a4  mov     rsi, [r11+40h]
0x1800206a8  mov     rsp, r11
0x1800206ab  pop     r15
0x1800206ad  pop     r14
0x1800206af  pop     r12
0x1800206b1  pop     rdi
0x1800206b2  pop     rbp
0x1800206b3  retn
```
