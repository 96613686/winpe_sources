# UnBCL::Path::GetFullPath(UnBCL::String const *)

- ea: `0x180049500`
- end: `0x180049881`
- name: `?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `897`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `17`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x180028470`
- `0x180029280`
- `0x180029b30`
- `0x18002a870`
- `0x18002bca0`
- `0x18002c4e0`
- `0x18002c640`
- `0x18002e060`
- `0x18002eb20`
- `0x1800306a0`
- `0x18003b2e0`
- `0x18003b5f0`
- `0x18003c0a0`
- `0x18003c3a0`
- `0x18003c680`
- `0x18003c960`
- `0x18003d910`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x1800098f0`
- `0x1800099f0`
- `0x180009e7c`
- `0x18000e980`
- `0x180011570`
- `0x180011f00`
- `0x180017e30`
- `0x18001e610`
- `0x1800477d0`
- `0x180048af8`
- `0x180048b40`
- `0x180049500`
- `0x18004a530`
- `0x18004a690`
- `0x18004a8b0`
- `0x18005b790`
- `0x18005c010`
- `0x18005dc40`
- `0x180064340`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180049657`
- `KERNEL32!GetFullPathNameW` at `0x180049657`
- `KERNEL32!GetLastError` at `0x1800497ea`
- `KERNEL32!GetLastError` at `0x1800497ea`

## string_xrefs

- `0x1800497b0`: `class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)`
- `0x18004980e`: `class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)`
- `0x18004985d`: `class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct UnBCL::String *__fastcall UnBCL::Path::GetFullPath(const struct UnBCL::String *a1)
{
  struct UnBCL::String *v2; // rax
  int v3; // esi
  LPCWSTR *v4; // rdi
  __int64 v5; // rax
  struct UnBCL::String *v6; // rax
  DWORD v7; // ebx
  WCHAR *Buffer; // rax
  DWORD FullPathNameW; // eax
  WCHAR *v10; // rbx
  const unsigned __int16 *v11; // rax
  __int64 v12; // rax
  struct UnBCL::String *v13; // rax
  struct UnBCL::String *v14; // rbx
  struct UnBCL::String *v15; // rax
  WCHAR *v17; // rbx
  const struct UnBCL::String *v18; // rax
  __int64 v19; // rax
  UnBCL::Win32Exception *v20; // rdi
  DWORD LastError; // ebx
  const struct UnBCL::String *v22; // rax
  __int64 v23; // rax
  WCHAR *v24; // rbx
  const struct UnBCL::String *v25; // rax
  __int64 v26; // rax
  void **v27; // [rsp+20h] [rbp-E0h] BYREF
  struct UnBCL::String *v28; // [rsp+28h] [rbp-D8h]
  void **v29; // [rsp+30h] [rbp-D0h] BYREF
  UnBCL::String *v30; // [rsp+38h] [rbp-C8h]
  _QWORD v31[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[48]; // [rsp+60h] [rbp-A0h] BYREF
  void **v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 pExceptionObject; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR FilePart; // [rsp+158h] [rbp+58h] BYREF
  UnBCL::Win32Exception *v36; // [rsp+160h] [rbp+60h]

  v31[2] = -2;
  if ( !a1 )
  {
    v24 = (WCHAR *)UnBCL::Object::operator new(0x38u);
    FilePart = v24;
    if ( v24 )
    {
      v25 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_1__1();
      v26 = UnBCL::ArgumentNullException::ArgumentNullException((UnBCL::ArgumentNullException *)v24, v25);
    }
    else
    {
      v26 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v26,
                         "class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) )
  {
    v17 = (WCHAR *)UnBCL::Object::operator new(0x38u);
    FilePart = v17;
    if ( v17 )
    {
      v18 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_2__0();
      v19 = UnBCL::ArgumentException::ArgumentException((UnBCL::ArgumentException *)v17, v18);
    }
    else
    {
      v19 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v19,
                         "class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  LODWORD(pExceptionObject) = 0;
  v2 = UnBCL::Path::WithoutLongPrefix(a1, (int *)&pExceptionObject);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v29, v2);
  v3 = 0;
  v4 = (LPCWSTR *)v30;
  v5 = *((_QWORD *)v30 + 2);
  if ( (const unsigned __int16 *)v5 != L"."
    && (!v5 || *(_DWORD *)v5 != 46 && (wchar_t *)v5 != L".." && (*(_WORD *)v5 != 46 || *(_DWORD *)(v5 + 2) != 46))
    && ((unsigned int)UnBCL::String::EndsWith(v30, 0x20u)
     || (unsigned int)UnBCL::String::EndsWith((UnBCL::String *)v4, 0x2Eu)) )
  {
    v6 = UnBCL::Path::WithLongPrefixStd(a1, 0);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v27, v6);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v29, v28);
    v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
    v3 = 1;
    v4 = (LPCWSTR *)v30;
  }
  v7 = 260;
  UnBCL::ArrayList<unsigned short>::ArrayList<unsigned short>(v32, 1);
  while ( 1 )
  {
    UnBCL::ArrayList<unsigned short>::Resize(v32, v7, 0);
    FilePart = 0;
    Buffer = (WCHAR *)UnBCL::ArrayList<unsigned short>::GetBuffer(v32, 0);
    FullPathNameW = GetFullPathNameW(v4[2], v7, Buffer, &FilePart);
    if ( !FullPathNameW )
    {
      v20 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v36 = v20;
      if ( v20 )
      {
        LastError = GetLastError();
        v22 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v29);
        v23 = UnBCL::Win32Exception::Win32Exception(v20, LastError, v22);
      }
      else
      {
        v23 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v23,
                           "class UnBCL::String *__cdecl UnBCL::Path::GetFullPath(const class UnBCL::String *)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    if ( FullPathNameW <= v7 )
      break;
    v7 = FullPathNameW;
  }
  v10 = (WCHAR *)UnBCL::Object::operator new(0x18u);
  FilePart = v10;
  if ( v10 )
  {
    v11 = (const unsigned __int16 *)UnBCL::ArrayList<unsigned short>::GetBuffer(v32, 0);
    v12 = UnBCL::String::String((UnBCL::String *)v10, v11);
  }
  else
  {
    v12 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v27, v12);
  if ( v3 )
  {
    LODWORD(FilePart) = 0;
    v13 = UnBCL::Path::WithoutLongPrefix(v28, (int *)&FilePart);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v31, v13);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v27, v31[1]);
    v31[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v31);
  }
  v14 = v28;
  if ( (int)pExceptionObject <= 0 )
  {
    if ( v28 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v28 + 2);
      v28 = 0;
    }
    else
    {
      v14 = 0;
    }
  }
  else
  {
    if ( (unsigned int)UnBCL::String::StartsWith(v28, L"\\\\", 1) )
      v15 = UnBCL::Path::WithLongPrefixUNC(v14, 0);
    else
      v15 = UnBCL::Path::WithLongPrefixStd(v14, 0);
    v14 = v15;
  }
  v27 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v27);
  UnBCL::ArrayList<unsigned short>::~ArrayList<unsigned short>(&v33);
  v33 = &UnBCL::Object::`vftable';
  v29 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v29);
  return v14;
}

```

## disassembly

```asm
0x180049500  push    rbp
0x180049502  push    rbx
0x180049503  push    rsi
0x180049504  push    rdi
0x180049505  push    r12
0x180049507  push    r14
0x180049509  push    r15
0x18004950b  lea     rbp, [rsp-10h]
0x180049510  sub     rsp, 110h
0x180049517  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFEh
0x180049520  mov     rbx, rcx
0x180049523  xor     r14d, r14d
0x180049526  test    rcx, rcx
0x180049529  jz      loc_180049832
0x18004952f  mov     rax, [rcx+10h]
0x180049533  cmp     [rax], r14w
0x180049537  jz      loc_180049785
0x18004953d  mov     dword ptr [rbp+40h+pExceptionObject], r14d
0x180049541  lea     rdx, [rbp+40h+pExceptionObject]; int *
0x180049545  call    ?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@AEAH@Z; UnBCL::Path::WithoutLongPrefix(UnBCL::String const *,int &)
0x18004954a  mov     rdx, rax
0x18004954d  lea     rcx, [rsp+140h+var_110]
0x180049552  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180049557  nop
0x180049558  mov     esi, r14d
0x18004955b  mov     rdi, [rsp+140h+var_108]
0x180049560  mov     rax, [rdi+10h]
0x180049564  lea     rcx, asc_180080E80; "."
0x18004956b  lea     r15, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180049572  cmp     rax, rcx
0x180049575  jz      loc_180049616
0x18004957b  lea     r12d, [r14+2Eh]
0x18004957f  test    rax, rax
0x180049582  jz      short loc_1800495B5
0x180049584  cmp     [rax], r12w
0x180049588  jnz     short loc_180049595
0x18004958a  cmp     [rax+2], r14w
0x18004958f  jz      loc_180049616
0x180049595  lea     rcx, asc_180080E84; ".."
0x18004959c  cmp     rax, rcx
0x18004959f  jz      short loc_180049616
0x1800495a1  cmp     [rax], r12w
0x1800495a5  jnz     short loc_1800495B5
0x1800495a7  cmp     [rax+2], r12w
0x1800495ac  jnz     short loc_1800495B5
0x1800495ae  cmp     [rax+4], r14w
0x1800495b3  jz      short loc_180049616
0x1800495b5  mov     edx, 20h ; ' '; unsigned __int16
0x1800495ba  mov     rcx, rdi; this
0x1800495bd  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x1800495c2  test    eax, eax
0x1800495c4  jnz     short loc_1800495D5
0x1800495c6  mov     edx, r12d; unsigned __int16
0x1800495c9  mov     rcx, rdi; this
0x1800495cc  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x1800495d1  test    eax, eax
0x1800495d3  jz      short loc_180049616
0x1800495d5  xor     edx, edx; int
0x1800495d7  mov     rcx, rbx; struct UnBCL::String *
0x1800495da  call    ?WithLongPrefixStd@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefixStd(UnBCL::String const *,int)
0x1800495df  mov     rdx, rax
0x1800495e2  lea     rcx, [rsp+140h+var_120]
0x1800495e7  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800495ec  nop
0x1800495ed  mov     rdx, [rsp+140h+var_118]
0x1800495f2  lea     rcx, [rsp+140h+var_110]
0x1800495f7  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x1800495fc  nop
0x1800495fd  mov     [rsp+140h+var_120], r15
0x180049602  lea     rcx, [rsp+140h+var_120]
0x180049607  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004960c  mov     esi, 1
0x180049611  mov     rdi, [rsp+140h+var_108]
0x180049616  mov     ebx, 104h
0x18004961b  mov     edx, 1
0x180049620  lea     rcx, [rsp+140h+var_E0]
0x180049625  call    ??0?$ArrayList@G@UnBCL@@QEAA@XZ; UnBCL::ArrayList<ushort>::ArrayList<ushort>(void)
0x18004962a  nop
0x18004962b  xor     r8d, r8d
0x18004962e  mov     edx, ebx
0x180049630  lea     rcx, [rsp+140h+var_E0]
0x180049635  call    ?Resize@?$ArrayList@G@UnBCL@@UEAAXHH@Z; UnBCL::ArrayList<ushort>::Resize(int,int)
0x18004963a  mov     [rbp+40h+FilePart], r14
0x18004963e  xor     edx, edx
0x180049640  lea     rcx, [rsp+140h+var_E0]
0x180049645  call    ?GetBuffer@?$ArrayList@G@UnBCL@@UEAAPEAGH@Z; UnBCL::ArrayList<ushort>::GetBuffer(int)
0x18004964a  lea     r9, [rbp+40h+FilePart]; lpFilePart
0x18004964e  mov     r8, rax; lpBuffer
0x180049651  mov     edx, ebx; nBufferLength
0x180049653  mov     rcx, [rdi+10h]; lpFileName
0x180049657  call    cs:__imp_GetFullPathNameW
0x18004965d  test    eax, eax
0x18004965f  jz      loc_1800497D4
0x180049665  cmp     eax, ebx
0x180049667  jbe     short loc_18004966D
0x180049669  mov     ebx, eax
0x18004966b  jmp     short loc_18004962B
0x18004966d  mov     ecx, 18h; unsigned __int64
0x180049672  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049677  mov     rbx, rax
0x18004967a  mov     [rbp+40h+FilePart], rax
0x18004967e  test    rax, rax
0x180049681  jz      short loc_18004969C
0x180049683  xor     edx, edx
0x180049685  lea     rcx, [rsp+140h+var_E0]
0x18004968a  call    ?GetBuffer@?$ArrayList@G@UnBCL@@UEAAPEAGH@Z; UnBCL::ArrayList<ushort>::GetBuffer(int)
0x18004968f  mov     rdx, rax; unsigned __int16 *
0x180049692  mov     rcx, rbx; this
0x180049695  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18004969a  jmp     short loc_18004969F
0x18004969c  mov     rax, r14
0x18004969f  mov     rdx, rax
0x1800496a2  lea     rcx, [rsp+140h+var_120]
0x1800496a7  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800496ac  nop
0x1800496ad  test    esi, esi
0x1800496af  jz      short loc_1800496F0
0x1800496b1  mov     dword ptr [rbp+40h+FilePart], r14d
0x1800496b5  lea     rdx, [rbp+40h+FilePart]; int *
0x1800496b9  mov     rcx, [rsp+140h+var_118]; struct UnBCL::String *
0x1800496be  call    ?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@AEAH@Z; UnBCL::Path::WithoutLongPrefix(UnBCL::String const *,int &)
0x1800496c3  mov     rdx, rax
0x1800496c6  lea     rcx, [rsp+140h+var_100]
0x1800496cb  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800496d0  nop
0x1800496d1  mov     rdx, [rsp+140h+var_F8]
0x1800496d6  lea     rcx, [rsp+140h+var_120]
0x1800496db  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x1800496e0  nop
0x1800496e1  mov     [rsp+140h+var_100], r15
0x1800496e6  lea     rcx, [rsp+140h+var_100]
0x1800496eb  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800496f0  mov     rbx, [rsp+140h+var_118]
0x1800496f5  cmp     dword ptr [rbp+40h+pExceptionObject], r14d
0x1800496f9  jle     short loc_180049770
0x1800496fb  mov     r8d, 1; int
0x180049701  lea     rdx, asc_18008970C; "\\\\"
0x180049708  mov     rcx, rbx; this
0x18004970b  call    ?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x180049710  xor     edx, edx; int
0x180049712  mov     rcx, rbx; struct UnBCL::String *
0x180049715  test    eax, eax
0x180049717  jz      short loc_180049720
0x180049719  call    ?WithLongPrefixUNC@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefixUNC(UnBCL::String const *,int)
0x18004971e  jmp     short loc_180049725
0x180049720  call    ?WithLongPrefixStd@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefixStd(UnBCL::String const *,int)
0x180049725  mov     rbx, rax
0x180049728  mov     [rsp+140h+var_120], r15
0x18004972d  lea     rcx, [rsp+140h+var_120]
0x180049732  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180049737  nop
0x180049738  lea     rcx, [rbp+40h+var_B0]
0x18004973c  call    ??1?$ArrayList@G@UnBCL@@UEAA@XZ; UnBCL::ArrayList<ushort>::~ArrayList<ushort>(void)
0x180049741  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180049748  mov     [rbp+40h+var_B0], rax
0x18004974c  mov     [rsp+140h+var_110], r15
0x180049751  lea     rcx, [rsp+140h+var_110]
0x180049756  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004975b  mov     rax, rbx
0x18004975e  add     rsp, 110h
0x180049765  pop     r15
0x180049767  pop     r14
0x180049769  pop     r12
0x18004976b  pop     rdi
0x18004976c  pop     rsi
0x18004976d  pop     rbx
0x18004976e  pop     rbp
0x18004976f  retn
0x180049770  test    rbx, rbx
0x180049773  jnz     short loc_18004977A
0x180049775  mov     rbx, r14
0x180049778  jmp     short loc_180049728
0x18004977a  lock dec dword ptr [rbx+8]
0x18004977e  mov     [rsp+140h+var_118], r14
0x180049783  jmp     short loc_180049728
0x180049785  mov     ecx, 38h ; '8'; unsigned __int64
0x18004978a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004978f  mov     rbx, rax
0x180049792  mov     [rbp+40h+FilePart], rax
0x180049796  test    rax, rax
0x180049799  jz      short loc_1800497AD
0x18004979b  call    UnBCL_____StringLiteral_2__0
0x1800497a0  mov     rdx, rax; struct UnBCL::String *
0x1800497a3  mov     rcx, rbx; this
0x1800497a6  call    ??0ArgumentException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ArgumentException::ArgumentException(UnBCL::String const *)
0x1800497ab  jmp     short loc_1800497B0
0x1800497ad  mov     rax, r14
0x1800497b0  lea     rdx, aClassUnbclStri_5; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x1800497b7  mov     rcx, rax
0x1800497ba  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800497bf  mov     [rbp+40h+pExceptionObject], rax
0x1800497c3  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800497ca  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800497ce  call    _CxxThrowException_0
0x1800497d4  mov     ecx, 40h ; '@'; unsigned __int64
0x1800497d9  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800497de  mov     rdi, rax
0x1800497e1  mov     [rbp+40h+arg_10], rax
0x1800497e5  test    rax, rax
0x1800497e8  jz      short loc_18004980B
0x1800497ea  call    cs:__imp_GetLastError
0x1800497f0  mov     ebx, eax
0x1800497f2  lea     rcx, [rsp+140h+var_110]
0x1800497f7  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x1800497fc  mov     r8, rax; struct UnBCL::String *
0x1800497ff  mov     edx, ebx; dwMessageId
0x180049801  mov     rcx, rdi; this
0x180049804  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x180049809  jmp     short loc_18004980E
0x18004980b  mov     rax, r14
0x18004980e  lea     rdx, aClassUnbclStri_5; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049815  mov     rcx, rax
0x180049818  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004981d  mov     [rbp+40h+pExceptionObject], rax
0x180049821  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x180049828  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18004982c  call    _CxxThrowException_0
0x180049832  mov     ecx, 38h ; '8'; unsigned __int64
0x180049837  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004983c  mov     rbx, rax
0x18004983f  mov     [rbp+40h+FilePart], rax
0x180049843  test    rax, rax
0x180049846  jz      short loc_18004985A
0x180049848  call    UnBCL_____StringLiteral_1__1
0x18004984d  mov     rdx, rax; struct UnBCL::String *
0x180049850  mov     rcx, rbx; this
0x180049853  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ArgumentNullException::ArgumentNullException(UnBCL::String const *)
0x180049858  jmp     short loc_18004985D
0x18004985a  mov     rax, r14
0x18004985d  lea     rdx, aClassUnbclStri_5; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049864  mov     rcx, rax
0x180049867  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004986c  mov     [rbp+40h+pExceptionObject], rax
0x180049870  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180049877  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18004987b  call    _CxxThrowException_0
```
