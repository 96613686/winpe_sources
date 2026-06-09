# CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)

- ea: `0x180004f98`
- end: `0x1800051df`
- name: `?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z`
- size: `583`
- prototype: `void __fastcall(CWdsDeviceControllerManager *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct CWdsComMetadataBuilder *, unsigned int, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800051e8`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`

## callees

- `0x180004f98`
- `0x1800071e4`
- `0x18000a5e8`
- `0x18000b228`
- `0x18000e65c`
- `0x180014d58`
- `0x1800150b8`

## pseudocode

```c
void __fastcall CWdsDeviceControllerManager::LogDeviceManagement(
        CWdsDeviceControllerManager *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct CWdsComMetadataBuilder *a5,
        char a6,
        unsigned int a7)
{
  int v7; // esi
  void *v8; // rbx
  unsigned int v9; // r12d
  const OLECHAR *v11; // r15
  const OLECHAR *v12; // r8
  unsigned int v14; // eax
  int v15; // edx
  int v16; // edx
  bool v17; // zf
  int v18; // ecx
  unsigned int Metadata; // eax
  const char *v20; // rdx
  unsigned int v21; // eax
  const char *v22; // rdx
  unsigned int v23; // ebx
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  __int64 *v28; // rdx
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  int v30; // [rsp+50h] [rbp-29h]
  int v31; // [rsp+54h] [rbp-25h]
  __int64 v32; // [rsp+60h] [rbp-19h]
  int v33; // [rsp+68h] [rbp-11h]
  int v34; // [rsp+6Ch] [rbp-Dh]
  __int64 v35; // [rsp+78h] [rbp-1h]
  int v36; // [rsp+80h] [rbp+7h]
  int v37; // [rsp+84h] [rbp+Bh]
  void *Block; // [rsp+C8h] [rbp+4Fh] BYREF

  v7 = a7;
  v8 = 0;
  Block = 0;
  v9 = a7 >> 31;
  LODWORD(v11) = (_DWORD)a4;
  v12 = &word_18001870C;
  if ( a2 == 3 )
  {
LABEL_6:
    v14 = (unsigned __int8)byte_18001DD41;
    v15 = (unsigned __int8)byte_18001DD41 >> 5;
    goto LABEL_7;
  }
  if ( a2 != 4 && a2 != 5 && a2 != 6 )
  {
    if ( a2 != 7 )
      return;
    goto LABEL_6;
  }
  v14 = (unsigned __int8)byte_18001DD41;
  v15 = (unsigned __int8)byte_18001DD41 >> 3;
LABEL_7:
  v16 = v15 & 1;
  if ( (a7 & 0x80000000) != 0 )
    v17 = ((v14 >> 4) & 1) == 0;
  else
    v17 = v16 == 0;
  if ( !v17 )
  {
    v18 = (int)a5;
    if ( !a3 )
      a3 = &word_18001870C;
    if ( !a4 )
      v11 = &word_18001870C;
    if ( a5 )
    {
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      Metadata = CWdsComMetadataBuilder::GetMetadata(a5, (struct CWdsMetadata *)&v29);
      if ( ElValidateWin32(
             Metadata,
             v20,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x807u) )
      {
        CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v29);
        return;
      }
      v21 = CWdsMetadata::ToLines((CWdsMetadata *)&v29, (unsigned __int16 **)&Block);
      v23 = ElValidateWin32(v21, v22, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x80Au);
      CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v29);
      v17 = v23 == 0;
      v8 = Block;
      if ( !v17 )
        goto LABEL_52;
      LOBYTE(v14) = byte_18001DD41;
      v12 = (const OLECHAR *)Block;
    }
    v24 = a2 - 3;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            if ( v27 != 1 )
              goto LABEL_52;
            if ( v7 < 0 )
            {
              if ( (v14 & 0x10) == 0 )
                goto LABEL_52;
              v28 = DeviceLookupFailed;
            }
            else
            {
              if ( (v14 & 0x20) == 0 )
                goto LABEL_52;
              v28 = DeviceLookup;
            }
          }
          else if ( v9 )
          {
            if ( (v14 & 0x10) == 0 )
              goto LABEL_52;
            v28 = DeviceModifyFailed;
          }
          else
          {
            if ( (v14 & 8) == 0 )
              goto LABEL_52;
            v28 = DeviceModified;
          }
        }
        else if ( v9 )
        {
          if ( (v14 & 0x10) == 0 )
            goto LABEL_52;
          v28 = DeviceDeleteFailed;
        }
        else
        {
          if ( (v14 & 8) == 0 )
            goto LABEL_52;
          v28 = DeviceDeleted;
        }
      }
      else if ( v9 )
      {
        if ( (v14 & 0x10) == 0 )
          goto LABEL_52;
        v28 = DeviceAddFailed;
      }
      else
      {
        if ( (v14 & 8) == 0 )
          goto LABEL_52;
        v28 = DeviceAdded;
      }
    }
    else if ( v9 )
    {
      if ( (v14 & 0x10) == 0 )
        goto LABEL_52;
      v28 = QueryControllersFailed;
    }
    else
    {
      if ( (v14 & 0x20) == 0 )
        goto LABEL_52;
      v28 = QueryControllers;
    }
    McTemplateU0zzzqd(v18, (_DWORD)v28, (_DWORD)a3, (_DWORD)v11, (__int64)v12, a6, v7);
LABEL_52:
    if ( v8 )
      operator delete(v8);
  }
}

```

## disassembly

```asm
0x180004f98  mov     rax, rsp
0x180004f9b  mov     [rax+10h], rbx
0x180004f9f  mov     [rax+18h], rsi
0x180004fa3  mov     [rax+8], rcx
0x180004fa7  push    rbp
0x180004fa8  push    rdi
0x180004fa9  push    r12
0x180004fab  push    r14
0x180004fad  push    r15
0x180004faf  lea     rbp, [rax-47h]
0x180004fb3  sub     rsp, 90h
0x180004fba  mov     esi, [rbp+3Fh+arg_30]
0x180004fbd  xor     ebx, ebx
0x180004fbf  mov     r12d, esi
0x180004fc2  mov     [rbp+3Fh+Block], rbx
0x180004fc6  shr     r12d, 1Fh
0x180004fca  mov     eax, edx
0x180004fcc  mov     r14, r8
0x180004fcf  mov     r15, r9
0x180004fd2  lea     r8, word_18001870C
0x180004fd9  mov     edi, edx
0x180004fdb  sub     eax, 3
0x180004fde  jz      short loc_180004FF8
0x180004fe0  sub     eax, 1
0x180004fe3  jz      short loc_180005018
0x180004fe5  sub     eax, 1
0x180004fe8  jz      short loc_180005018
0x180004fea  sub     eax, 1
0x180004fed  jz      short loc_180005018
0x180004fef  sub     eax, 1
0x180004ff2  jnz     loc_1800051C3
0x180004ff8  movzx   eax, cs:byte_18001DD41
0x180004fff  mov     edx, eax
0x180005001  shr     edx, 5
0x180005004  mov     ecx, eax
0x180005006  and     edx, 1
0x180005009  shr     ecx, 4
0x18000500c  and     ecx, 1
0x18000500f  test    r12d, r12d
0x180005012  jnz     short loc_180005026
0x180005014  test    edx, edx
0x180005016  jmp     short loc_180005028
0x180005018  movzx   eax, cs:byte_18001DD41
0x18000501f  mov     edx, eax
0x180005021  shr     edx, 3
0x180005024  jmp     short loc_180005004
0x180005026  test    ecx, ecx
0x180005028  jz      loc_1800051C3
0x18000502e  mov     rcx, [rbp+3Fh+arg_20]; this
0x180005032  test    r14, r14
0x180005035  cmovz   r14, r8
0x180005039  test    r15, r15
0x18000503c  cmovz   r15, r8
0x180005040  test    rcx, rcx
0x180005043  jz      loc_1800050D3
0x180005049  and     [rbp+3Fh+var_70], rbx
0x18000504d  lea     rdx, [rbp+3Fh+var_70]; struct CWdsMetadata *
0x180005051  and     [rbp+3Fh+var_68], ebx
0x180005054  and     [rbp+3Fh+var_64], ebx
0x180005057  and     [rbp+3Fh+var_58], rbx
0x18000505b  and     [rbp+3Fh+var_50], ebx
0x18000505e  and     [rbp+3Fh+var_4C], ebx
0x180005061  and     [rbp+3Fh+var_40], rbx
0x180005065  and     [rbp+3Fh+var_38], ebx
0x180005068  and     [rbp+3Fh+var_34], ebx
0x18000506b  call    ?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z; CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)
0x180005070  mov     r9d, 807h; unsigned int
0x180005076  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000507d  mov     ecx, eax; unsigned int
0x18000507f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005084  lea     rcx, [rbp+3Fh+var_70]; this
0x180005088  test    eax, eax
0x18000508a  jz      short loc_180005096
0x18000508c  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005091  jmp     loc_1800051C3
0x180005096  lea     rdx, [rbp+3Fh+Block]; unsigned __int16 **
0x18000509a  call    ?ToLines@CWdsMetadata@@QEBAKPEAPEAG@Z; CWdsMetadata::ToLines(ushort * *)
0x18000509f  mov     r9d, 80Ah; unsigned int
0x1800050a5  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800050ac  mov     ecx, eax; unsigned int
0x1800050ae  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800050b3  lea     rcx, [rbp+3Fh+var_70]; this
0x1800050b7  mov     ebx, eax
0x1800050b9  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800050be  test    ebx, ebx
0x1800050c0  mov     rbx, [rbp+3Fh+Block]
0x1800050c4  jnz     loc_1800051B6
0x1800050ca  mov     al, cs:byte_18001DD41
0x1800050d0  mov     r8, rbx
0x1800050d3  sub     edi, 3
0x1800050d6  jz      loc_18000517E
0x1800050dc  sub     edi, 1
0x1800050df  jz      short loc_18000515F
0x1800050e1  sub     edi, 1
0x1800050e4  jz      short loc_180005140
0x1800050e6  sub     edi, 1
0x1800050e9  jz      short loc_18000511D
0x1800050eb  cmp     edi, 1
0x1800050ee  jnz     loc_1800051B6
0x1800050f4  test    esi, esi
0x1800050f6  js      short loc_18000510C
0x1800050f8  test    al, 20h
0x1800050fa  jz      loc_1800051B6
0x180005100  lea     rdx, DeviceLookup
0x180005107  jmp     loc_18000519B
0x18000510c  test    al, 10h
0x18000510e  jz      loc_1800051B6
0x180005114  lea     rdx, DeviceLookupFailed
0x18000511b  jmp     short loc_18000519B
0x18000511d  test    r12d, r12d
0x180005120  jnz     short loc_180005133
0x180005122  test    al, 8
0x180005124  jz      loc_1800051B6
0x18000512a  lea     rdx, DeviceModified
0x180005131  jmp     short loc_18000519B
0x180005133  test    al, 10h
0x180005135  jz      short loc_1800051B6
0x180005137  lea     rdx, DeviceModifyFailed
0x18000513e  jmp     short loc_18000519B
0x180005140  test    r12d, r12d
0x180005143  jnz     short loc_180005152
0x180005145  test    al, 8
0x180005147  jz      short loc_1800051B6
0x180005149  lea     rdx, DeviceDeleted
0x180005150  jmp     short loc_18000519B
0x180005152  test    al, 10h
0x180005154  jz      short loc_1800051B6
0x180005156  lea     rdx, DeviceDeleteFailed
0x18000515d  jmp     short loc_18000519B
0x18000515f  test    r12d, r12d
0x180005162  jnz     short loc_180005171
0x180005164  test    al, 8
0x180005166  jz      short loc_1800051B6
0x180005168  lea     rdx, DeviceAdded
0x18000516f  jmp     short loc_18000519B
0x180005171  test    al, 10h
0x180005173  jz      short loc_1800051B6
0x180005175  lea     rdx, DeviceAddFailed
0x18000517c  jmp     short loc_18000519B
0x18000517e  test    r12d, r12d
0x180005181  jnz     short loc_180005190
0x180005183  test    al, 20h
0x180005185  jz      short loc_1800051B6
0x180005187  lea     rdx, QueryControllers
0x18000518e  jmp     short loc_18000519B
0x180005190  test    al, 10h
0x180005192  jz      short loc_1800051B6
0x180005194  lea     rdx, QueryControllersFailed
0x18000519b  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18000519e  mov     r9, r15
0x1800051a1  mov     [rsp+0B0h+var_80], esi
0x1800051a5  mov     [rsp+0B0h+var_88], eax
0x1800051a9  mov     qword ptr [rsp+0B0h+var_90], r8
0x1800051ae  mov     r8, r14
0x1800051b1  call    McTemplateU0zzzqd
0x1800051b6  test    rbx, rbx
0x1800051b9  jz      short loc_1800051C3
0x1800051bb  mov     rcx, rbx; Block
0x1800051be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051c3  lea     r11, [rsp+0B0h+var_20]
0x1800051cb  mov     rbx, [r11+38h]
0x1800051cf  mov     rsi, [r11+40h]
0x1800051d3  mov     rsp, r11
0x1800051d6  pop     r15
0x1800051d8  pop     r14
0x1800051da  pop     r12
0x1800051dc  pop     rdi
0x1800051dd  pop     rbp
0x1800051de  retn
```
