# EnumFilesAndRecurse(URI_ENUM_DATA *,IIS_VDIR *,IIS_VDIR_PARENT *,uint,uint)

- ea: `0x18001efa4`
- end: `0x18001f122`
- name: `?EnumFilesAndRecurse@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@PEAVIIS_VDIR_PARENT@@II@Z`
- size: `382`
- prototype: `__int64 __usercall@<rax>(struct URI_ENUM_DATA *@<rcx>, struct IIS_VDIR *@<rdx>, struct IIS_VDIR_PARENT *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f3f0`

## callees

- `0x1800043b0`
- `0x18001efa4`
- `0x18001f3f0`
- `0x18001faf0`
- `0x18001fc18`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001f0b2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001f0b2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f109`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f109`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001f0ec`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001f0f6`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001f0ec`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001f0f6`

## pseudocode

```c
__int64 __fastcall EnumFilesAndRecurse(
        struct URI_ENUM_DATA *a1,
        struct IIS_VDIR *a2,
        struct IIS_VDIR_PARENT *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // r12
  int started; // edi
  int v8; // r8d
  int v9; // r15d
  _BYTE *v10; // rax
  int v11; // ecx
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  __int64 v13; // r8
  HANDLE hFindFile; // [rsp+60h] [rbp+8h] BYREF
  struct IIS_VDIR_PARENT *v16; // [rsp+70h] [rbp+18h]

  v16 = a3;
  v5 = a4;
  hFindFile = (HANDLE)-1LL;
  started = StartUriEnum(a1, a2, a4, a5, &hFindFile);
  if ( started < 0 )
    goto LABEL_21;
  v9 = 1;
  if ( hFindFile == (HANDLE)-1LL )
    goto LABEL_21;
  while ( 1 )
  {
    v10 = (char *)a1 + 164;
    if ( *((_WORD *)a1 + 104) != 46 )
      break;
    if ( *((_WORD *)a1 + 105) && (*((_WORD *)a1 + 105) != 46 || *((_WORD *)a1 + 106)) )
    {
      v10 = (char *)a1 + 164;
      break;
    }
LABEL_17:
    if ( !FindNextFileW(hFindFile, (LPWIN32_FIND_DATAW)((char *)a1 + 164)) )
      goto LABEL_20;
  }
  if ( (*v10 & 0x10) == 0 )
    goto LABEL_17;
  v11 = *((_DWORD *)a1 + 36);
  if ( (v11 & 8) == 0 && (*v10 & 2) != 0 )
    goto LABEL_17;
  if ( (v11 & 0x10) == 0 && (*v10 & 4) != 0 )
    goto LABEL_17;
  if ( v16 )
  {
    Key = STATIC_WSTRING_HASH::FindKey(
            (struct IIS_VDIR_PARENT *)((char *)v16 + 24),
            (const unsigned __int16 *)a1 + 104,
            v8);
    if ( (-(__int64)(Key != 0) & ((unsigned __int64)Key - 24)) != 0 )
      goto LABEL_17;
  }
  started = UpdateUriEnumData(a1, v5, a5, (const unsigned __int16 *)a1 + 104, 1);
  if ( started >= 0 )
  {
    started = EnumUriWorker(a1);
    if ( started >= 0 )
      goto LABEL_17;
  }
  v9 = 0;
LABEL_20:
  *((_DWORD *)a1 + 38) = v9;
LABEL_21:
  v13 = a5;
  *(_WORD *)(*((_QWORD *)a1 + 8) + 2 * v5) = 0;
  *(_WORD *)(*((_QWORD *)a1 + 15) + 2 * v13) = 0;
  STRU::SyncWithBuffer((struct URI_ENUM_DATA *)((char *)a1 + 32));
  STRU::SyncWithBuffer((struct URI_ENUM_DATA *)((char *)a1 + 88));
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001efa4  mov     r11, rsp
0x18001efa7  mov     [r11+10h], rbx
0x18001efab  mov     [r11+18h], r8
0x18001efaf  push    rbp
0x18001efb0  push    rsi
0x18001efb1  push    rdi
0x18001efb2  push    r12
0x18001efb4  push    r15
0x18001efb6  sub     rsp, 30h
0x18001efba  mov     r12d, r9d
0x18001efbd  lea     rax, [r11+8]
0x18001efc1  mov     r9d, [rsp+58h+arg_20]; unsigned int
0x18001efc9  mov     r8d, r12d; unsigned int
0x18001efcc  mov     rbx, rcx
0x18001efcf  mov     qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x18001efd7  mov     [r11-38h], rax
0x18001efdb  call    ?StartUriEnum@@YAJPEAVURI_ENUM_DATA@@PEAVIIS_VDIR@@IIPEAPEAX@Z; StartUriEnum(URI_ENUM_DATA *,IIS_VDIR *,uint,uint,void * *)
0x18001efe0  xor     r9d, r9d
0x18001efe3  mov     edi, eax
0x18001efe5  test    eax, eax
0x18001efe7  js      loc_18001F0CE
0x18001efed  cmp     [rsp+58h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001eff3  lea     r15d, [r9+1]
0x18001eff7  jz      loc_18001F0CE
0x18001effd  lea     rbp, [rbx+0D0h]
0x18001f004  lea     rsi, [rbx+0A4h]
0x18001f00b  cmp     word ptr [rbp+0], 2Eh ; '.'
0x18001f010  mov     rax, rsi
0x18001f013  jnz     short loc_18001F031
0x18001f015  cmp     [rbp+2], r9w
0x18001f01a  jz      loc_18001F0AA
0x18001f020  cmp     word ptr [rbp+2], 2Eh ; '.'
0x18001f025  jnz     short loc_18001F02E
0x18001f027  cmp     [rbp+4], r9w
0x18001f02c  jz      short loc_18001F0AA
0x18001f02e  mov     rax, rsi
0x18001f031  test    byte ptr [rax], 10h
0x18001f034  jz      short loc_18001F0AA
0x18001f036  mov     ecx, [rbx+90h]
0x18001f03c  test    cl, 8
0x18001f03f  jnz     short loc_18001F046
0x18001f041  test    byte ptr [rax], 2
0x18001f044  jnz     short loc_18001F0AA
0x18001f046  test    cl, 10h
0x18001f049  jnz     short loc_18001F050
0x18001f04b  test    byte ptr [rax], 4
0x18001f04e  jnz     short loc_18001F0AA
0x18001f050  mov     rax, [rsp+58h+arg_10]
0x18001f055  test    rax, rax
0x18001f058  jz      short loc_18001F075
0x18001f05a  lea     rcx, [rax+18h]; this
0x18001f05e  mov     rdx, rbp; unsigned __int16 *
0x18001f061  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18001f066  lea     rcx, [rax-18h]
0x18001f06a  neg     rax
0x18001f06d  sbb     rax, rax
0x18001f070  test    rcx, rax
0x18001f073  jnz     short loc_18001F0AA
0x18001f075  mov     r8d, [rsp+58h+arg_20]; unsigned int
0x18001f07d  mov     r9, rbp; unsigned __int16 *
0x18001f080  mov     edx, r12d; unsigned int
0x18001f083  mov     [rsp+58h+var_38], r15d; int
0x18001f088  mov     rcx, rbx; struct URI_ENUM_DATA *
0x18001f08b  call    ?UpdateUriEnumData@@YAJPEAVURI_ENUM_DATA@@IIPEBGH@Z; UpdateUriEnumData(URI_ENUM_DATA *,uint,uint,ushort const *,int)
0x18001f090  xor     r9d, r9d
0x18001f093  mov     edi, eax
0x18001f095  test    eax, eax
0x18001f097  js      short loc_18001F0C4
0x18001f099  mov     rcx, rbx; struct URI_ENUM_DATA *
0x18001f09c  call    ?EnumUriWorker@@YAJPEAVURI_ENUM_DATA@@@Z; EnumUriWorker(URI_ENUM_DATA *)
0x18001f0a1  xor     r9d, r9d
0x18001f0a4  mov     edi, eax
0x18001f0a6  test    eax, eax
0x18001f0a8  js      short loc_18001F0C4
0x18001f0aa  mov     rcx, [rsp+58h+hFindFile]; hFindFile
0x18001f0af  mov     rdx, rsi; lpFindFileData
0x18001f0b2  call    cs:__imp_FindNextFileW
0x18001f0b8  xor     r9d, r9d
0x18001f0bb  test    eax, eax
0x18001f0bd  jz      short loc_18001F0C7
0x18001f0bf  jmp     loc_18001F00B
0x18001f0c4  mov     r15d, r9d
0x18001f0c7  mov     [rbx+98h], r15d
0x18001f0ce  mov     rdx, [rbx+40h]
0x18001f0d2  lea     rcx, [rbx+20h]
0x18001f0d6  mov     r8d, [rsp+58h+arg_20]
0x18001f0de  mov     [rdx+r12*2], r9w
0x18001f0e3  mov     rdx, [rbx+78h]
0x18001f0e7  mov     [rdx+r8*2], r9w
0x18001f0ec  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001f0f2  lea     rcx, [rbx+58h]
0x18001f0f6  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001f0fc  cmp     [rsp+58h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001f102  jz      short loc_18001F10F
0x18001f104  mov     rcx, [rsp+58h+hFindFile]; hFindFile
0x18001f109  call    cs:__imp_FindClose
0x18001f10f  mov     rbx, [rsp+58h+arg_8]
0x18001f114  mov     eax, edi
0x18001f116  add     rsp, 30h
0x18001f11a  pop     r15
0x18001f11c  pop     r12
0x18001f11e  pop     rdi
0x18001f11f  pop     rsi
0x18001f120  pop     rbp
0x18001f121  retn
```
