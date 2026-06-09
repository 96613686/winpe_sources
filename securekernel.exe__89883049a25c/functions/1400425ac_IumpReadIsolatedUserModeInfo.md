# IumpReadIsolatedUserModeInfo

- ea: `0x1400425ac`
- end: `0x140042759`
- name: `IumpReadIsolatedUserModeInfo`
- size: `429`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140043654`

## callees

- `0x1400425ac`
- `0x14005adbc`
- `0x1400f3620`
- `0x1400f38f0`
- `0x1400f9a80`
- `0x1400fc554`

## pseudocode

```c
__int64 __fastcall IumpReadIsolatedUserModeInfo(void *a1, unsigned int a2, _DWORD *a3, char a4)
{
  __int64 result; // rax
  char v9; // cl
  char v10; // r10
  int v11; // edx
  char v12; // r8
  char v13; // cl
  char v14; // r10
  char v15; // cl
  _BYTE v16[16]; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-98h]
  __int128 Src; // [rsp+A0h] [rbp-38h] BYREF

  memset_0(v16, 0, 0x68u);
  if ( a2 >= 0x10 )
  {
    Src = 0;
    SkmmQueryStrongCodeFeatures(v16);
    v9 = (2 * (v17 & 1)) | 4;
    if ( (v17 & 2) == 0 )
      v9 = 2 * (v17 & 1);
    v10 = v9 | 8;
    if ( (v17 & 4) != 0 )
      v10 = v9;
    v11 = (v17 >> 6) & 1;
    v12 = v11 != 0 ? 2 : 0;
    v13 = v12;
    if ( (v17 & 0x200) != 0 )
    {
      v13 = v11 != 0 ? 10 : 8;
      v12 = v13;
    }
    v14 = v10 | 1;
    LOBYTE(Src) = v14;
    v15 = v13 | 0x10;
    if ( (v17 & 0x400) == 0 )
      v15 = v12;
    BYTE1(Src) = v15;
    LOBYTE(Src) = v14 | (4 * (*(_BYTE *)(SkeLoaderBlock + 1968) & 4));
    LOBYTE(Src) = Src | (*(_QWORD *)(SkeLoaderBlock + 1408) != 0 ? 0x20 : 0);
    BYTE2(Src) = BYTE2(Src) & 0xFE | ((*(_DWORD *)(SkeLoaderBlock + 1860) & 0x40) != 0);
    if ( a4 )
      RtlCopyToUser(a1, &Src, 0x10u);
    else
      RtlCopyVolatileMemory(a1, &Src, 0x10u);
    result = 0;
  }
  else
  {
    result = 3221225476LL;
  }
  *a3 = 16;
  return result;
}

```

## disassembly

```asm
0x1400425ac  mov     [rsp+arg_8], rbx
0x1400425b1  mov     [rsp+arg_18], r9b
0x1400425b6  push    rsi
0x1400425b7  push    r14
0x1400425b9  push    r15
0x1400425bb  sub     rsp, 0C0h
0x1400425c2  mov     rax, cs:__security_cookie
0x1400425c9  xor     rax, rsp
0x1400425cc  mov     [rsp+0D8h+var_28], rax
0x1400425d4  mov     r15b, r9b
0x1400425d7  mov     rsi, r8
0x1400425da  mov     ebx, edx
0x1400425dc  mov     r14, rcx
0x1400425df  mov     [rsp+0D8h+var_B0], r8
0x1400425e4  xor     edx, edx; Val
0x1400425e6  lea     r8d, [rdx+68h]; Size
0x1400425ea  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1400425ef  call    memset_0
0x1400425f4  cmp     ebx, 10h
0x1400425f7  jnb     short loc_140042603
0x1400425f9  mov     eax, 0C0000004h
0x1400425fe  jmp     loc_14004272D
0x140042603  xorps   xmm0, xmm0
0x140042606  movups  [rsp+0D8h+Src], xmm0
0x14004260e  lea     rcx, [rsp+0D8h+var_A8]
0x140042613  call    SkmmQueryStrongCodeFeatures
0x140042618  mov     r9d, [rsp+0D8h+var_98]
0x14004261d  mov     al, r9b
0x140042620  and     al, 1
0x140042622  add     al, al
0x140042624  movzx   r8d, al
0x140042628  mov     r11b, 2
0x14004262b  mov     al, r8b
0x14004262e  mov     bl, 4
0x140042630  or      al, bl
0x140042632  movzx   ecx, al
0x140042635  test    r11b, r9b
0x140042638  cmovz   ecx, r8d
0x14004263c  movzx   edx, cl
0x14004263f  mov     al, dl
0x140042641  or      al, 8
0x140042643  movzx   r10d, al
0x140042647  test    bl, r9b
0x14004264a  cmovnz  r10d, edx
0x14004264e  mov     edx, r9d
0x140042651  shr     edx, 6
0x140042654  and     edx, 1
0x140042657  mov     eax, edx
0x140042659  neg     eax
0x14004265b  sbb     r8b, r8b
0x14004265e  and     r8b, r11b
0x140042661  mov     eax, edx
0x140042663  neg     eax
0x140042665  sbb     cl, cl
0x140042667  and     cl, r11b
0x14004266a  bt      r9d, 9
0x14004266f  jnb     short loc_14004267E
0x140042671  neg     edx
0x140042673  sbb     cl, cl
0x140042675  and     cl, r11b
0x140042678  add     cl, 8
0x14004267b  mov     r8b, cl
0x14004267e  or      r10b, 1
0x140042682  mov     byte ptr [rsp+0D8h+Src], r10b
0x14004268a  or      cl, 10h
0x14004268d  movzx   ecx, cl
0x140042690  movzx   eax, r8b
0x140042694  test    [rsp+0D8h+var_98], 400h
0x14004269c  cmovz   ecx, eax
0x14004269f  mov     byte ptr [rsp+0D8h+Src+1], cl
0x1400426a6  mov     r8, cs:SkeLoaderBlock
0x1400426ad  mov     dl, [r8+7B0h]
0x1400426b4  and     dl, bl
0x1400426b6  shl     dl, 2
0x1400426b9  or      dl, r10b
0x1400426bc  mov     byte ptr [rsp+0D8h+Src], dl
0x1400426c3  mov     rax, [r8+580h]
0x1400426ca  neg     rax
0x1400426cd  sbb     cl, cl
0x1400426cf  and     cl, 20h
0x1400426d2  or      cl, dl
0x1400426d4  mov     byte ptr [rsp+0D8h+Src], cl
0x1400426db  mov     edx, [r8+744h]
0x1400426e2  shr     edx, 6
0x1400426e5  and     dl, 1
0x1400426e8  mov     al, byte ptr [rsp+0D8h+Src+2]
0x1400426ef  and     al, 0FEh
0x1400426f1  or      dl, al
0x1400426f3  mov     byte ptr [rsp+0D8h+Src+2], dl
0x1400426fa  mov     r8d, 10h; Size
0x140042700  lea     rdx, [rsp+0D8h+Src]; Src
0x140042708  mov     rcx, r14; void *
0x14004270b  test    r15b, r15b
0x14004270e  jz      short loc_140042717
0x140042710  call    RtlCopyToUser
0x140042715  jmp     short loc_14004271C
0x140042717  call    RtlCopyVolatileMemory
0x14004271c  xor     eax, eax
0x14004271e  mov     [rsp+0D8h+var_B4], eax
0x140042722  jmp     short loc_14004272D
0x140042724  mov     [rsp+0D8h+var_B4], eax
0x140042728  mov     rsi, [rsp+0D8h+var_B0]
0x14004272d  mov     dword ptr [rsi], 10h
0x140042733  mov     rcx, [rsp+0D8h+var_28]
0x14004273b  xor     rcx, rsp; StackCookie
0x14004273e  call    __security_check_cookie
0x140042743  mov     rbx, [rsp+0D8h+arg_8]
0x14004274b  add     rsp, 0C0h
0x140042752  pop     r15
0x140042754  pop     r14
0x140042756  pop     rsi
0x140042757  retn
0x1400fa616  push    rbp
0x1400fa618  sub     rsp, 20h
0x1400fa61c  mov     rbp, rdx
0x1400fa61f  xor     eax, eax
0x1400fa621  cmp     [rbp+0F8h], al
0x1400fa627  setnz   al
0x1400fa62a  mov     [rbp+20h], eax
0x1400fa62d  mov     eax, [rbp+20h]
0x1400fa630  add     rsp, 20h
0x1400fa634  pop     rbp
0x1400fa635  retn
```
