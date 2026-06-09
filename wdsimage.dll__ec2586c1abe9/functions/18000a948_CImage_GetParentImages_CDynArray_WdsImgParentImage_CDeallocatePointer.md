# CImage::GetParentImages(CDynArray<WdsImgParentImage *,CDeallocatePointer> *)

- ea: `0x18000a948`
- end: `0x18000ab4d`
- name: `?GetParentImages@CImage@@AEAAJPEAV?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c77c`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x180003a60`
- `0x1800073c0`
- `0x180008c40`
- `0x18000a948`
- `0x18000ae64`
- `0x18000b108`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000ff10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aafd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aafd`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000a99d`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000a99d`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aa92`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aa92`

## pseudocode

```c
__int64 __fastcall CImage::GetParentImages(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r14
  __int64 v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // rdi
  const unsigned __int16 *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // esi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  _DWORD v21[4]; // [rsp+20h] [rbp-1D8h] BYREF
  _BYTE v22[32]; // [rsp+30h] [rbp-1C8h] BYREF
  __int128 v23; // [rsp+50h] [rbp-1A8h]

  v2 = 0;
  v3 = 0;
  if ( *(_DWORD *)(a1 + 364) )
  {
    while ( 1 )
    {
      v6 = *(_QWORD *)(a1 + 368);
      v21[0] = 0;
      v7 = WdsIdnCompareFilePaths(*(_QWORD *)(v6 + 8 * v3), *(_QWORD *)(a1 + 88), v21);
      if ( (unsigned int)ElValidateWin32_4((unsigned int)v7, v8, v9, 1118) )
        break;
      if ( v21[0]
        && (unsigned int)CImage::IsValidImage(*(const unsigned __int16 **)(*(_QWORD *)(a1 + 368) + 8 * v3), 0x206u) )
      {
        v10 = (unsigned __int16 **)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v11 = v10;
        if ( !v10 )
          return (unsigned int)-2147024882;
        *(_OWORD *)v10 = 0;
        *((_OWORD *)v10 + 1) = 0;
        *((_OWORD *)v10 + 2) = 0;
        v12 = *(const unsigned __int16 **)(*(_QWORD *)(a1 + 368) + 8 * v3);
        CImage::CImage((CImage *)v22);
        v2 = CImage::Initialize((CImage *)v22, v12, 1, 16);
        if ( (int)ElValidateHr_5(v2, v13, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3788) >= 0 )
          *(_OWORD *)v11 = v23;
        CImage::~CImage((CImage *)v22);
        if ( (int)ElValidateHr_5(v2, v14, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1130) < 0 )
          goto LABEL_16;
        v15 = DuplicateStringW(*(const unsigned __int16 **)(*(_QWORD *)(a1 + 368) + 8 * v3), v11 + 2);
        if ( (unsigned int)ElValidateWin32_4((unsigned int)v15, v16, v17, 1135)
          || (v15 = CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(a2, v11),
              (unsigned int)ElValidateWin32_4((unsigned int)v15, v18, v19, 1138)) )
        {
          if ( v15 > 0 )
            v2 = (unsigned __int16)v15 | 0x80070000;
          else
            v2 = v15;
LABEL_16:
          WdsImgParentImage::~WdsImgParentImage((WdsImgParentImage *)v11);
          operator delete(v11);
          return v2;
        }
      }
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 364) )
        return v2;
    }
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    else
      return (unsigned int)v7;
  }
  return v2;
}

```

## disassembly

```asm
0x18000a948  mov     [rsp+arg_10], rbx
0x18000a94d  push    rbp
0x18000a94e  push    rsi
0x18000a94f  push    rdi
0x18000a950  push    r14
0x18000a952  push    r15
0x18000a954  sub     rsp, 1D0h
0x18000a95b  mov     rax, cs:__security_cookie
0x18000a962  xor     rax, rsp
0x18000a965  mov     [rsp+1F8h+var_38], rax
0x18000a96d  xor     ebx, ebx
0x18000a96f  xor     r14d, r14d
0x18000a972  mov     r15, rdx
0x18000a975  mov     rbp, rcx
0x18000a978  cmp     [rcx+16Ch], ebx
0x18000a97e  jbe     loc_18000AB23
0x18000a984  mov     rcx, [rbp+170h]
0x18000a98b  lea     r8, [rsp+1F8h+var_1D8]
0x18000a990  and     [rsp+1F8h+var_1D8], 0
0x18000a995  mov     rdx, [rbp+58h]
0x18000a999  mov     rcx, [rcx+r14*8]
0x18000a99d  call    cs:__imp_WdsIdnCompareFilePaths
0x18000a9a4  nop     dword ptr [rax+rax+00h]
0x18000a9a9  mov     ecx, eax
0x18000a9ab  mov     r9d, 45Eh
0x18000a9b1  mov     edi, eax
0x18000a9b3  call    ElValidateWin32_4
0x18000a9b8  test    eax, eax
0x18000a9ba  jnz     loc_18000AB12
0x18000a9c0  cmp     [rsp+1F8h+var_1D8], eax
0x18000a9c4  jz      loc_18000AACF
0x18000a9ca  mov     rcx, [rbp+170h]
0x18000a9d1  mov     edx, 206h; unsigned int
0x18000a9d6  mov     rcx, [rcx+r14*8]; unsigned __int16 *
0x18000a9da  call    ?IsValidImage@CImage@@SAHPEBGK@Z; CImage::IsValidImage(ushort const *,ulong)
0x18000a9df  test    eax, eax
0x18000a9e1  jz      loc_18000AACF
0x18000a9e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a9ee  mov     ecx, 30h ; '0'; unsigned __int64
0x18000a9f3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a9f8  mov     rdi, rax
0x18000a9fb  test    rax, rax
0x18000a9fe  jz      loc_18000AB0B
0x18000aa04  xorps   xmm0, xmm0
0x18000aa07  lea     rcx, [rsp+1F8h+var_1C8]; this
0x18000aa0c  movups  xmmword ptr [rax], xmm0
0x18000aa0f  movups  xmmword ptr [rax+10h], xmm0
0x18000aa13  movups  xmmword ptr [rax+20h], xmm0
0x18000aa17  mov     rax, [rbp+170h]
0x18000aa1e  mov     rbx, [rax+r14*8]
0x18000aa22  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x18000aa27  mov     r9d, 10h; unsigned int
0x18000aa2d  lea     rcx, [rsp+1F8h+var_1C8]; this
0x18000aa32  mov     rdx, rbx; unsigned __int16 *
0x18000aa35  lea     r8d, [r9-0Fh]; unsigned int
0x18000aa39  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x18000aa3e  mov     r9d, 0ECCh
0x18000aa44  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000aa4b  mov     ecx, eax
0x18000aa4d  mov     ebx, eax
0x18000aa4f  call    ElValidateHr_5
0x18000aa54  test    eax, eax
0x18000aa56  js      short loc_18000AA61
0x18000aa58  movaps  xmm0, [rsp+1F8h+var_1A8]
0x18000aa5d  movdqu  xmmword ptr [rdi], xmm0
0x18000aa61  lea     rcx, [rsp+1F8h+var_1C8]; this
0x18000aa66  call    ??1CImage@@UEAA@XZ; CImage::~CImage(void)
0x18000aa6b  mov     r9d, 46Ah
0x18000aa71  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000aa78  mov     ecx, ebx
0x18000aa7a  call    ElValidateHr_5
0x18000aa7f  test    eax, eax
0x18000aa81  js      short loc_18000AAF2
0x18000aa83  mov     rcx, [rbp+170h]
0x18000aa8a  lea     rdx, [rdi+10h]
0x18000aa8e  mov     rcx, [rcx+r14*8]
0x18000aa92  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000aa99  nop     dword ptr [rax+rax+00h]
0x18000aa9e  mov     ecx, eax
0x18000aaa0  mov     r9d, 46Fh
0x18000aaa6  mov     esi, eax
0x18000aaa8  call    ElValidateWin32_4
0x18000aaad  test    eax, eax
0x18000aaaf  jnz     short loc_18000AAE1
0x18000aab1  mov     rdx, rdi
0x18000aab4  mov     rcx, r15
0x18000aab7  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x18000aabc  mov     r9d, 472h
0x18000aac2  mov     ecx, eax
0x18000aac4  mov     esi, eax
0x18000aac6  call    ElValidateWin32_4
0x18000aacb  test    eax, eax
0x18000aacd  jnz     short loc_18000AAE1
0x18000aacf  inc     r14d
0x18000aad2  cmp     r14d, [rbp+16Ch]
0x18000aad9  jb      loc_18000A984
0x18000aadf  jmp     short loc_18000AB23
0x18000aae1  test    esi, esi
0x18000aae3  jg      short loc_18000AAE9
0x18000aae5  mov     ebx, esi
0x18000aae7  jmp     short loc_18000AAF2
0x18000aae9  movzx   ebx, si
0x18000aaec  or      ebx, 80070000h
0x18000aaf2  mov     rcx, rdi; this
0x18000aaf5  call    ??1WdsImgParentImage@@QEAA@XZ; WdsImgParentImage::~WdsImgParentImage(void)
0x18000aafa  mov     rcx, rdi
0x18000aafd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ab04  nop     dword ptr [rax+rax+00h]
0x18000ab09  jmp     short loc_18000AB23
0x18000ab0b  mov     ebx, 8007000Eh
0x18000ab10  jmp     short loc_18000AB23
0x18000ab12  test    edi, edi
0x18000ab14  jg      short loc_18000AB1A
0x18000ab16  mov     ebx, edi
0x18000ab18  jmp     short loc_18000AB23
0x18000ab1a  movzx   ebx, di
0x18000ab1d  or      ebx, 80070000h
0x18000ab23  mov     eax, ebx
0x18000ab25  mov     rcx, [rsp+1F8h+var_38]
0x18000ab2d  xor     rcx, rsp; StackCookie
0x18000ab30  call    __security_check_cookie
0x18000ab35  mov     rbx, [rsp+1F8h+arg_10]
0x18000ab3d  add     rsp, 1D0h
0x18000ab44  pop     r15
0x18000ab46  pop     r14
0x18000ab48  pop     rdi
0x18000ab49  pop     rsi
0x18000ab4a  pop     rbp
0x18000ab4b  retn
```
