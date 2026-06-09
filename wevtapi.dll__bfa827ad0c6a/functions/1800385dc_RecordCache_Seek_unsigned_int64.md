# RecordCache::Seek(unsigned __int64)

- ea: `0x1800385dc`
- end: `0x180038714`
- name: `?Seek@RecordCache@@IEAAX_K@Z`
- size: `312`
- prototype: `void __fastcall(RecordCache *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800377a8`
- `0x180037cac`
- `0x180037d98`
- `0x18003871c`
- `0x18003881c`

## callees

- `0x180023548`
- `0x1800373ec`
- `0x1800385dc`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038682`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038678`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038678`

## pseudocode

```c
void __fastcall RecordCache::Seek(RecordCache *this, unsigned __int64 a2)
{
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v5; // [rsp+30h] [rbp-20h]
  int v6; // [rsp+38h] [rbp-18h]
  int v7; // [rsp+3Ch] [rbp-14h]
  int v8; // [rsp+40h] [rbp-10h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+60h] [rbp+10h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( a2 > *((_QWORD *)this + 1) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
    }
    v5 = 0;
    v6 = 13;
    v7 = -1;
    pExceptionObject = 0;
    v8 = 394;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !SetFilePointerEx(*((HANDLE *)this + 7), (LARGE_INTEGER)(*((_QWORD *)this + 122) + a2), &NewFilePointer, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    v5 = 0;
    v6 = LastError;
    v7 = -1;
    pExceptionObject = 0;
    v8 = 403;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)this + 2) = RecordCache::GetFilePosition(this);
}

```

## disassembly

```asm
0x1800385dc  mov     [rsp-8+arg_8], rbx
0x1800385e1  push    rbp
0x1800385e2  mov     rbp, rsp
0x1800385e5  sub     rsp, 50h
0x1800385e9  mov     rbx, rcx
0x1800385ec  mov     qword ptr [rbp+NewFilePointer], 0
0x1800385f4  cmp     rdx, [rcx+8]
0x1800385f8  jbe     short loc_180038666
0x1800385fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038601  lea     rax, WPP_GLOBAL_Control
0x180038608  mov     ebx, 0Dh
0x18003860d  cmp     rcx, rax
0x180038610  jz      short loc_180038634
0x180038612  test    byte ptr [rcx+1Ch], 1
0x180038616  jz      short loc_180038634
0x180038618  cmp     byte ptr [rcx+19h], 2
0x18003861c  jb      short loc_180038634
0x18003861e  mov     rcx, [rcx+10h]
0x180038622  lea     edx, [rbx+5]
0x180038625  mov     r9d, ebx
0x180038628  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003862f  call    WPP_SF_D
0x180038634  xorps   xmm0, xmm0
0x180038637  mov     [rbp+var_20], 0
0x18003863f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038646  mov     [rbp+var_18], ebx
0x180038649  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003864d  mov     [rbp+var_14], 0FFFFFFFFh
0x180038654  movdqu  [rbp+pExceptionObject], xmm0
0x180038659  mov     [rbp+var_10], 18Ah
0x180038660  call    _CxxThrowException_0
0x180038666  add     rdx, [rcx+3D0h]; liDistanceToMove
0x18003866d  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180038671  mov     rcx, [rcx+38h]; hFile
0x180038675  xor     r9d, r9d; dwMoveMethod
0x180038678  call    cs:__imp_SetFilePointerEx
0x18003867e  test    eax, eax
0x180038680  jnz     short loc_1800386FD
0x180038682  call    cs:__imp_GetLastError
0x180038688  mov     ebx, eax
0x18003868a  mov     eax, 507h
0x18003868f  test    ebx, ebx
0x180038691  cmovz   ebx, eax
0x180038694  mov     rcx, cs:WPP_GLOBAL_Control
0x18003869b  lea     rax, WPP_GLOBAL_Control
0x1800386a2  cmp     rcx, rax
0x1800386a5  jz      short loc_1800386CB
0x1800386a7  test    byte ptr [rcx+1Ch], 1
0x1800386ab  jz      short loc_1800386CB
0x1800386ad  cmp     byte ptr [rcx+19h], 2
0x1800386b1  jb      short loc_1800386CB
0x1800386b3  mov     rcx, [rcx+10h]
0x1800386b7  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800386be  mov     edx, 13h
0x1800386c3  mov     r9d, ebx
0x1800386c6  call    WPP_SF_D
0x1800386cb  xorps   xmm0, xmm0
0x1800386ce  mov     [rbp+var_20], 0
0x1800386d6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800386dd  mov     [rbp+var_18], ebx
0x1800386e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800386e4  mov     [rbp+var_14], 0FFFFFFFFh
0x1800386eb  movdqu  [rbp+pExceptionObject], xmm0
0x1800386f0  mov     [rbp+var_10], 193h
0x1800386f7  call    _CxxThrowException_0
0x1800386fd  mov     rcx, rbx; this
0x180038700  call    ?GetFilePosition@RecordCache@@QEAA_KXZ; RecordCache::GetFilePosition(void)
0x180038705  mov     [rbx+10h], rax
0x180038709  mov     rbx, [rsp+50h+arg_8]
0x18003870e  add     rsp, 50h
0x180038712  pop     rbp
0x180038713  retn
```
