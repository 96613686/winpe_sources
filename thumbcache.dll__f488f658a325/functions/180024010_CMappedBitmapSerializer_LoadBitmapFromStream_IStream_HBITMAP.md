# CMappedBitmapSerializer::LoadBitmapFromStream(IStream *,HBITMAP__ * *)

- ea: `0x180024010`
- end: `0x1800241c2`
- name: `?LoadBitmapFromStream@CMappedBitmapSerializer@@UEBAJPEAUIStream@@PEAPEAUHBITMAP__@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(CMappedBitmapSerializer *this, struct IStream *, HBITMAP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180024010`
- `0x1800241d0`
- `0x180035830`
- `0x1800364ac`
- `0x180049010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18002411d`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180024181`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18002411d`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180024181`
- `GDI32!DeleteObject` at `0x1800241b7`
- `GDI32!DeleteObject` at `0x1800241b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMappedBitmapSerializer::LoadBitmapFromStream(
        CMappedBitmapSerializer *this,
        struct IStream *a2,
        HBITMAP *a3)
{
  unsigned int v5; // edi
  void *hSection; // r15
  DWORD v7; // r14d
  DWORD offset; // ebx
  DWORD biSize; // eax
  int v10; // esi
  __int64 v11; // rcx
  HBITMAP v12; // rbx
  void *ppvBits; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-C0h] BYREF
  BITMAPINFO pbmi; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(v16, 0, 0x48Cu);
  v5 = _LoadAndValidateBitmapHeaderFromStream(a2, (struct BITMAPOFFSETFILEHEADER *)v16);
  if ( (v5 & 0x80000000) == 0 )
  {
    ppvBits = 0;
    hSection = 0;
    v7 = 0;
    offset = 0;
    biSize = pbmi.bmiHeader.biSize;
    if ( pbmi.bmiHeader.biSize != 40 )
      biSize = 40;
    pbmi.bmiHeader.biSize = biSize;
    v5 = -2147467259;
    v10 = -2147467259;
    v11 = 0;
    v15 = 0;
    if ( a2 )
    {
      (**(void (__fastcall ***)(struct IStream *, GUID *, __int64 *))a2)(
        a2,
        &GUID_e237bfd4_55c8_471c_864b_f39e6844c388,
        &v15);
      v11 = v15;
    }
    if ( v11 )
    {
      hSection = *(void **)(v11 + 48);
      if ( hSection )
      {
        v10 = 0;
        offset = *(_DWORD *)(v11 + 24) + *(_DWORD *)(v11 + 56) - *(_DWORD *)(v11 + 32);
        v7 = *(_DWORD *)(v11 + 40) - *(_DWORD *)(v11 + 24);
      }
      else
      {
        v10 = -2147467259;
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v10 < 0
      || v7 < pbmi.bmiHeader.biSizeImage
      || (v12 = CreateDIBSection(0, &pbmi, 0, &ppvBits, hSection, offset)) == 0 )
    {
      v12 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
      if ( !v12 )
        return v5;
      if ( (*(int (__fastcall **)(struct IStream *, void *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
             a2,
             ppvBits,
             pbmi.bmiHeader.biSizeImage,
             0) < 0 )
      {
        DeleteObject(v12);
        return v5;
      }
    }
    *a3 = v12;
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180024010  mov     [rsp-8+arg_0], rbx
0x180024015  push    rbp
0x180024016  push    rsi
0x180024017  push    rdi
0x180024018  push    r12
0x18002401a  push    r13
0x18002401c  push    r14
0x18002401e  push    r15
0x180024020  lea     rbp, [rsp-3E0h]
0x180024028  sub     rsp, 4E0h
0x18002402f  mov     rax, cs:__security_cookie
0x180024036  xor     rax, rsp
0x180024039  mov     [rbp+410h+var_40], rax
0x180024040  mov     r13, r8
0x180024043  mov     r12, rdx
0x180024046  xor     edx, edx; Val
0x180024048  mov     r8d, 48Ch; Size
0x18002404e  lea     rcx, [rsp+510h+var_4D0]; void *
0x180024053  call    memset_0
0x180024058  lea     rdx, [rsp+510h+var_4D0]; struct BITMAPOFFSETFILEHEADER *
0x18002405d  mov     rcx, r12; struct IStream *
0x180024060  call    ?_LoadAndValidateBitmapHeaderFromStream@@YAJPEAUIStream@@PEAUBITMAPOFFSETFILEHEADER@@@Z; _LoadAndValidateBitmapHeaderFromStream(IStream *,BITMAPOFFSETFILEHEADER *)
0x180024065  mov     edi, eax
0x180024067  test    eax, eax
0x180024069  js      loc_180024131
0x18002406f  mov     [rsp+510h+ppvBits], 0
0x180024078  xor     r15d, r15d
0x18002407b  xor     r14d, r14d
0x18002407e  xor     ebx, ebx
0x180024080  mov     eax, [rsp+510h+pbmi.bmiHeader.biSize]
0x180024084  lea     ecx, [rbx+28h]
0x180024087  cmp     eax, ecx
0x180024089  cmovnz  eax, ecx
0x18002408c  mov     [rsp+510h+pbmi.bmiHeader.biSize], eax
0x180024090  mov     edi, 80004005h
0x180024095  mov     esi, edi
0x180024097  xor     ecx, ecx
0x180024099  mov     [rsp+510h+var_4D8], rcx
0x18002409e  test    r12, r12
0x1800240a1  jz      short loc_1800240C3
0x1800240a3  mov     rax, [r12]
0x1800240a7  lea     r8, [rsp+510h+var_4D8]
0x1800240ac  lea     rdx, _GUID_e237bfd4_55c8_471c_864b_f39e6844c388
0x1800240b3  mov     rcx, r12
0x1800240b6  mov     rax, [rax]
0x1800240b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240be  mov     rcx, [rsp+510h+var_4D8]
0x1800240c3  test    rcx, rcx
0x1800240c6  jz      short loc_1800240E8
0x1800240c8  mov     r15, [rcx+30h]
0x1800240cc  test    r15, r15
0x1800240cf  jz      loc_18002415D
0x1800240d5  xor     esi, esi
0x1800240d7  mov     ebx, [rcx+38h]
0x1800240da  sub     ebx, [rcx+20h]
0x1800240dd  add     ebx, [rcx+18h]
0x1800240e0  mov     r14d, [rcx+28h]
0x1800240e4  sub     r14d, [rcx+18h]
0x1800240e8  test    rcx, rcx
0x1800240eb  jz      short loc_1800240FA
0x1800240ed  mov     rax, [rcx]
0x1800240f0  mov     rax, [rax+10h]
0x1800240f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240f9  nop
0x1800240fa  test    esi, esi
0x1800240fc  js      short loc_180024161
0x1800240fe  cmp     r14d, [rsp+510h+pbmi.bmiHeader.biSizeImage]
0x180024103  jb      short loc_180024161
0x180024105  mov     [rsp+510h+offset], ebx; offset
0x180024109  mov     [rsp+510h+hSection], r15; hSection
0x18002410e  lea     r9, [rsp+510h+ppvBits]; ppvBits
0x180024113  xor     r8d, r8d; usage
0x180024116  lea     rdx, [rsp+510h+pbmi]; pbmi
0x18002411b  xor     ecx, ecx; hdc
0x18002411d  call    cs:__imp_CreateDIBSection
0x180024123  mov     rbx, rax
0x180024126  test    rax, rax
0x180024129  jz      short loc_180024161
0x18002412b  mov     [r13+0], rbx
0x18002412f  xor     edi, edi
0x180024131  mov     eax, edi
0x180024133  mov     rcx, [rbp+410h+var_40]
0x18002413a  xor     rcx, rsp; StackCookie
0x18002413d  call    __security_check_cookie
0x180024142  mov     rbx, [rsp+510h+arg_0]
0x18002414a  add     rsp, 4E0h
0x180024151  pop     r15
0x180024153  pop     r14
0x180024155  pop     r13
0x180024157  pop     r12
0x180024159  pop     rdi
0x18002415a  pop     rsi
0x18002415b  pop     rbp
0x18002415c  retn
0x18002415d  mov     esi, edi
0x18002415f  jmp     short loc_1800240E8
0x180024161  mov     [rsp+510h+offset], 0; offset
0x180024169  mov     [rsp+510h+hSection], 0; hSection
0x180024172  lea     r9, [rsp+510h+ppvBits]; ppvBits
0x180024177  xor     r8d, r8d; usage
0x18002417a  lea     rdx, [rsp+510h+pbmi]; pbmi
0x18002417f  xor     ecx, ecx; hdc
0x180024181  call    cs:__imp_CreateDIBSection
0x180024187  mov     rbx, rax
0x18002418a  test    rax, rax
0x18002418d  jz      short loc_180024131
0x18002418f  mov     rax, [r12]
0x180024193  xor     r9d, r9d
0x180024196  mov     r8d, [rsp+510h+pbmi.bmiHeader.biSizeImage]
0x18002419b  mov     rdx, [rsp+510h+ppvBits]
0x1800241a0  mov     rcx, r12
0x1800241a3  mov     rax, [rax+18h]
0x1800241a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ac  test    eax, eax
0x1800241ae  jns     loc_18002412B
0x1800241b4  mov     rcx, rbx; ho
0x1800241b7  call    cs:__imp_DeleteObject
0x1800241bd  jmp     loc_180024131
```
